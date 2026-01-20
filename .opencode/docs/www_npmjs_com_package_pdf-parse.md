# pdf-parse - npm

> Source: https://www.npmjs.com/package/pdf-parse
> Cached: 2026-01-20T14:11:02.501Z

---

# pdf-parse

[](#pdf-parse)
**Pure TypeScript, cross-platform module for extracting text, images, and tables from PDFs.**

**Run 🤗 directly in your browser or in Node!**
 
 
[](https://www.npmjs.com/package/pdf-parse)
[](https://www.npmjs.com/package/pdf-parse)
[](https://www.npmjs.com/package/pdf-parse)
[](https://github.com/mehmet-kozan/pdf-parse/actions/workflows/test.yml)
[](https://github.com/mehmet-kozan/pdf-parse/actions/workflows/test_integration.yml)
[](https://biomejs.dev)
[](https://vitest.dev)
[](https://codecov.io/github/mehmet-kozan/pdf-parse)
[](https://mehmet-kozan.github.io/pdf-parse/)

## Getting Started with v2 (Coming from v1)

[](#getting-started-with-v2-coming-from-v1)
// v1
// const pdf = require('pdf-parse');
// pdf(buffer).then(result => console.log(result.text));

// v2
const { PDFParse } = require('pdf-parse');
// import { PDFParse } from 'pdf-parse';

async function run() {
	const parser = new PDFParse({ url: 'https://bitcoin.org/bitcoin.pdf' });

	const result = await parser.getText();
	console.log(result.text);
}

run();
Features [](https://mehmet-kozan.github.io/pdf-parse/)
[](#features-)

- CJS, ESM, Node.js, and browser support.

- Can be integrated with `React`, `Vue`, `Angular`, or any other web framework.

**Command-line interface** for quick PDF processing: [`CLI Documentation`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/command-line.md)

- [`Security Policy`](https://github.com/mehmet-kozan/pdf-parse?tab=security-ov-file#security-policy)

Retrieve headers and validate PDF : [`getHeader`](#getheader--node-utility-pdf-header-retrieval-and-validation)

Extract document info : [`getInfo`](#getinfo--extract-metadata-and-document-information)

Extract page text : [`getText`](#gettext--extract-text)

Render pages as PNG : [`getScreenshot`](#getscreenshot--render-pages-as-png)

Extract embedded images : [`getImage`](#getimage--extract-embedded-images)

Detect and extract tabular data : [`getTable`](#gettable--extract-tabular-data)

Well-covered with [`unit tests`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests)

[`Integration tests`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/integration) to validate end-to-end behavior across environments.
- See [LoadParameters](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/options.md#load-parameters) and [ParseParameters](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/options.md#parse-parameters) for all available options.

- Examples: [`live demo`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/reports/demo/), [`examples`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/examples/), [`tests`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/) and [`tests example`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/) folders.

- Supports: [`Next.js + Vercel`](https://github.com/mehmet-kozan/vercel-next-app-demo), Netlify, AWS Lambda, Cloudflare Workers.

## Installation

[](#installation)
npm install pdf-parse
# or
pnpm add pdf-parse
# or
yarn add pdf-parse
# or
bun add pdf-parse
### CLI Installation

[](#cli-installation)
For command-line usage, install the package globally:

npm install -g pdf-parse
Or use it directly with npx:

npx pdf-parse --help
For detailed CLI documentation and usage examples, see: [CLI Documentation](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/command-line.md)

## Usage

[](#usage)

`getHeader` — Node Utility: PDF Header Retrieval and Validation[](#getheader--node-utility-pdf-header-retrieval-and-validation)
// Important: getHeader is available from the 'pdf-parse/node' submodule
import { getHeader } from 'pdf-parse/node';

// Retrieve HTTP headers and file size without downloading the full file.
// Pass `true` to check PDF magic bytes via range request.
// Optionally validates PDFs by fetching the first 4 bytes (magic bytes).
// Useful for checking file existence, size, and type before full parsing.
// Node only, will not work in browser environments.
const result = await getHeader('https://bitcoin.org/bitcoin.pdf', true);

console.log(`Status: ${result.status}`);
console.log(`Content-Length: ${result.size}`);
console.log(`Is PDF: ${result.isPdf}`);
console.log(`Headers:`, result.headers);

`getInfo` — Extract Metadata and Document Information[](#getinfo--extract-metadata-and-document-information)
import { readFile } from 'node:fs/promises';
import { PDFParse } from 'pdf-parse';

const link = 'https://mehmet-kozan.github.io/pdf-parse/pdf/climate.pdf';
// const buffer = await readFile('reports/pdf/climate.pdf');
// const parser = new PDFParse({ data: buffer });

const parser = new PDFParse({ url: link });
const result = await parser.getInfo({ parsePageInfo: true });
await parser.destroy();

console.log(`Total pages: ${result.total}`);
console.log(`Title: ${result.info?.Title}`);
console.log(`Author: ${result.info?.Author}`);
console.log(`Creator: ${result.info?.Creator}`);
console.log(`Producer: ${result.info?.Producer}`);

// Access parsed date information
const dates = result.getDateNode();
console.log(`Creation Date: ${dates.CreationDate}`);
console.log(`Modification Date: ${dates.ModDate}`);

// Links, pageLabel, width, height (when `parsePageInfo` is true)
console.log('Per-page information:');
console.log(JSON.stringify(result.pages, null, 2));

`getText` — Extract Text[](#gettext--extract-text)
import { PDFParse } from 'pdf-parse';

const parser = new PDFParse({ url: 'https://bitcoin.org/bitcoin.pdf' });
const result = await parser.getText();
// to extract text from page 3 only:
// const result = await parser.getText({ partial: [3] });
await parser.destroy();
console.log(result.text);
For a complete list of configuration options, see:

- [LoadParameters](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/options.md#load-parameters)

- [ParseParameters](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/options.md#parse-parameters)

Usage Examples:

Parse password protected PDF:  [`password.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/password.test.ts)

Parse only specific pages: [`specific-pages.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/specific-pages.test.ts)

Parse embedded hyperlinks: [`hyperlink.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/hyperlink.test.ts)

Set verbosity level: [`password.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/password.test.ts)

Load PDF from URL: [`url.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/url.test.ts)

Load PDF from base64 data: [`base64.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/base64.test.ts)

Loading large files (> 5 MB): [`large-file.test.ts`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/tests/unit/test-example/large-file.test.ts)

`getScreenshot` — Render Pages as PNG[](#getscreenshot--render-pages-as-png)
import { readFile, writeFile } from 'node:fs/promises';
import { PDFParse } from 'pdf-parse';

const link = 'https://bitcoin.org/bitcoin.pdf';
// const buffer = await readFile('reports/pdf/bitcoin.pdf');
// const parser = new PDFParse({ data: buffer });

const parser = new PDFParse({ url: link });

// scale:1 for original page size.
// scale:1.5 50% bigger.
const result = await parser.getScreenshot({ scale: 1.5 });

await parser.destroy();
await writeFile('bitcoin.png', result.pages[0].data);
Usage Examples:

Limit output resolution or specific pages using [ParseParameters](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/options.md#parse-parameters)

`getScreenshot({scale:1.5})` — Increase rendering scale (higher DPI / larger image)

`getScreenshot({desiredWidth:1024})` — Request a target width in pixels; height scales to keep aspect ratio

`imageDataUrl` (default: `true`) — include base64 data URL string in the result.

`imageBuffer` (default: `true`) — include a binary buffer for each image.
- Select specific pages with `partial` (e.g. `getScreenshot({ partial: [1,3] })`)

`partial` overrides `first`/`last`.
- Use `first` to render the first N pages (e.g. `getScreenshot({ first: 3 })`).

- Use `last` to render the last N pages (e.g. `getScreenshot({ last: 2 })`).

- When both `first` and `last` are provided they form an inclusive range (`first..last`).

`getImage` — Extract Embedded Images[](#getimage--extract-embedded-images)
import { readFile, writeFile } from 'node:fs/promises';
import { PDFParse } from 'pdf-parse';

const link = new URL('https://mehmet-kozan.github.io/pdf-parse/pdf/image-test.pdf');
// const buffer = await readFile('reports/pdf/image-test.pdf');
// const parser = new PDFParse({ data: buffer });

const parser = new PDFParse({ url: link });
const result = await parser.getImage();
await parser.destroy();

await writeFile('adobe.png', result.pages[0].images[0].data);
Usage Examples:

Exclude images with width or height <= 50 px: `getImage({ imageThreshold: 50 })`

- Default `imageThreshold` is `80` (pixels)

- Useful for excluding tiny decorative or tracking images.

- To disable size-based filtering and include all images, set `imageThreshold: 0`.

`imageDataUrl` (default: `true`) — include base64 data URL string in the result.

`imageBuffer` (default: `true`) — include a binary buffer for each image.
Extract images from specific pages: `getImage({ partial: [2,4] })`

`getTable` — Extract Tabular Data[](#gettable--extract-tabular-data)
import { readFile } from 'node:fs/promises';
import { PDFParse } from 'pdf-parse';

const link = new URL('https://mehmet-kozan.github.io/pdf-parse/pdf/simple-table.pdf');
// const buffer = await readFile('reports/pdf/simple-table.pdf');
// const parser = new PDFParse({ data: buffer });

const parser = new PDFParse({ url: link });
const result = await parser.getTable();
await parser.destroy();

// Pretty-print each row of the first table
for (const row of result.pages[0].tables[0]) {
	console.log(JSON.stringify(row));
}
## Exception Handling & Type Usage

[](#exception-handling--type-usage)
import type { LoadParameters, ParseParameters, TextResult } from 'pdf-parse';
import { PasswordException, PDFParse, VerbosityLevel } from 'pdf-parse';

const loadParams: LoadParameters = {
	url: 'https://mehmet-kozan.github.io/pdf-parse/pdf/password-123456.pdf',
	verbosity: VerbosityLevel.WARNINGS,
	password: 'abcdef',
};

const parseParams: ParseParameters = {
	first: 1,
};

// Initialize the parser class without executing any code yet
const parser = new PDFParse(loadParams);

function handleResult(result: TextResult) {
	console.log(result.text);
}

try {
	const result = await parser.getText(parseParams);
	handleResult(result);
} catch (error) {
	// InvalidPDFException
	// PasswordException
	// FormatError
	// ResponseException
	// AbortException
	// UnknownErrorException
	if (error instanceof PasswordException) {
		console.error('Password must be 123456\n', error);
	} else {
		throw error;
	}
} finally {
	// Always call destroy() to free memory
	await parser.destroy();
}
Web / Browser [](https://www.jsdelivr.com/package/npm/pdf-parse)
[](#web--browser-)

- Can be integrated into `React`, `Vue`, `Angular`, or any other web framework.

**Live Demo:** [`https://mehmet-kozan.github.io/pdf-parse/`](https://mehmet-kozan.github.io/pdf-parse/)

**Demo Source:** [`reports/demo`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/reports/demo)

**ES Module**:  `pdf-parse.es.js` **UMD/Global**: `pdf-parse.umd.js`

- For browser build, set the `web worker` explicitly.

### CDN Usage

[](#cdn-usage)
<!-- ES Module -->
<script type="module">

  import {PDFParse} from 'https://cdn.jsdelivr.net/npm/pdf-parse@latest/dist/pdf-parse/web/pdf-parse.es.js';
  //// Available Worker Files
  // pdf.worker.mjs
  // pdf.worker.min.mjs
  // If you use a custom build or host pdf.worker.mjs yourself, configure worker accordingly.
  PDFParse.setWorker('https://cdn.jsdelivr.net/npm/pdf-parse@latest/dist/pdf-parse/web/pdf.worker.mjs');

  const parser = new PDFParse({url:'https://mehmet-kozan.github.io/pdf-parse/pdf/bitcoin.pdf'});
  const result = await parser.getText();

  console.log(result.text)
</script>
**CDN Options: [https://www.jsdelivr.com/package/npm/pdf-parse](https://www.jsdelivr.com/package/npm/pdf-parse)**

- `https://cdn.jsdelivr.net/npm/pdf-parse@latest/dist/pdf-parse/web/pdf-parse.es.js`

- `https://cdn.jsdelivr.net/npm/pdf-parse@2.4.5/dist/pdf-parse/web/pdf-parse.es.js`

- `https://cdn.jsdelivr.net/npm/pdf-parse@latest/dist/pdf-parse/web/pdf-parse.umd.js`

- `https://cdn.jsdelivr.net/npm/pdf-parse@2.4.5/dist/pdf-parse/web/pdf-parse.umd.js`

**Worker Options:**

- `https://cdn.jsdelivr.net/npm/pdf-parse@latest/dist/pdf-parse/web/pdf.worker.mjs`

- `https://cdn.jsdelivr.net/npm/pdf-parse@latest/dist/pdf-parse/web/pdf.worker.min.mjs`

## Similar Packages

[](#similar-packages)

[pdf2json](https://www.npmjs.com/package/pdf2json) — Buggy, memory leaks, uncatchable errors in some PDF files.

[pdfdataextract](https://www.npmjs.com/package/pdfdataextract) — `pdf-parse`-based

[unpdf](https://www.npmjs.com/package/unpdf) — `pdf-parse`-based

[pdf-extract](https://www.npmjs.com/package/pdf-extract) — Non-cross-platform, depends on xpdf

[j-pdfjson](https://www.npmjs.com/package/j-pdfjson) — Fork of pdf2json

[pdfreader](https://www.npmjs.com/package/pdfreader) — Uses pdf2json

[pdf-extract](https://www.npmjs.com/package/pdf-extract) — Non-cross-platform, depends on xpdf

> 
**Benchmark Note:** The benchmark currently runs only against `pdf2json`. I don't know the current state of `pdf2json` — the original reason for creating `pdf-parse` was to work around stability issues with `pdf2json`. I deliberately did not include `pdf-parse` or other `pdf.js`-based packages in the benchmark because dependencies conflict. If you have recommendations for additional packages to include, please open an issue, see [`benchmark results`](https://mehmet-kozan.github.io/pdf-parse/benchmark.html).

## Supported Node.js Versions(20.x, 22.x, 23.x, 24.x)

[](#supported-nodejs-versions20x-22x-23x-24x)

- Supported: Node.js 20 (>= 20.16.0), Node.js 22 (>= 22.3.0), Node.js 23 (>= 23.0.0), and Node.js 24 (>= 24.0.0).

- Not supported: Node.js 21.x, and Node.js 19.x and earlier.

Integration tests run on Node.js 20–24, see [`test_integration.yml`](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/.github/workflows/test_integration.yml).

### Unsupported Node.js Versions (18.x, 19.x, 21.x)

[](#unsupported-nodejs-versions-18x-19x-21x)
Requires additional setup see [docs/troubleshooting.md](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/troubleshooting.md).

## Worker Configuration & Troubleshooting

[](#worker-configuration--troubleshooting)
See [docs/troubleshooting.md](https://github.com/mehmet-kozan/pdf-parse/blob/HEAD/docs/troubleshooting.md) for detailed troubleshooting ste

... [Content truncated]