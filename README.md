I have a large Starlight documentation site with many Markdown/MDX docs containing heavy KaTeX/math content.

The build runs out of memory during Astro’s content sync phase, before page generation starts.

The reproduction repo is https://github.com/integrable/astrov7/

The failure happens after:

[content] Syncing content

and then Node/V8 eventually aborts with:

FATAL ERROR: Ineffective mark-compacts near heap limit Allocation failed - JavaScript heap out of memory

This appears to be a scalability issue in Astro’s content layer for renderable Markdown/MDX entries. My current understanding is that Astro’s glob() content loader eagerly renders Markdown/MDX entries and stores the rendered output in the global content data store. For Starlight docs pages with heavy KaTeX, the rendered HTML is much larger than the source Markdown, so syncing content can consume several GB of heap and eventually crash.

The KaTeX warnings printed before the crash do not seem to be the direct cause; they are warnings, and the process continues until memory is exhausted.

Steps to Reproduce:

```
git clone https://github.com/integrable/astrov7.git
cd astrov7
npm ci
rm -rf .astro dist node_modules/.astro
npm run build
```

Actual Result:

The build starts syncing content:

15:52:45 [content] Syncing content

Then several KaTeX warnings are printed, for example:

LaTeX-incompatible input and strict mode is set to 'warn': In LaTeX, \ or \newline does nothing in display mode [newLineInDisplayMode]

After several minutes, Node runs out of memory:

<--- Last few GCs --->

[93872:0x8b540c000] 178849 ms: Scavenge (interleaved) 4093.3 (4108.7) -> 4093.1 (4109.7) MB, pooled: 0 MB, 3.96 / 0.00 ms (average mu = 0.288, current mu = 0.234) allocation failure;
[93872:0x8b540c000] 179724 ms: Mark-Compact (reduce) 4094.0 (4109.7) -> 4093.9 (4108.2) MB, pooled: 0 MB, 630.04 / 0.00 ms (+ 9.1 ms in 14 steps since start of marking, biggest step 5.0 ms, walltime since start of marking 647 ms) (average mu = 0.286, c
FATAL ERROR: Ineffective mark-compacts near heap limit Allocation failed - JavaScript heap out of memory

zsh: abort npm run build

Related issue:

This is related to, but different from, the previous large content-store dev issue:

#17220

That issue was about dev mode returning empty collections when importing a large content data-store virtual module. This report is about build/content sync exhausting memory before page generation because the content store becomes too large when rendered Markdown/KaTeX output is eagerly retained.
