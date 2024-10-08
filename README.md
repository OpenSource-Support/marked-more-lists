# TODO:

- [ ] Write extension in `/src/index.js`
- [ ] Write tests in `/spec/index.test.js`
- [ ] Uncomment release in `/.github/workflows/main.yml`

# marked-more-lists

This extension for the [marked](https://marked.js.org/) library adds support for rendering ordered lists with various
`type` attributes. It allows Markdown lists that start with `a.`, `A.`, `i.`, `I.`, and other patterns to be rendered
as `<ol>` elements with corresponding `type` values (e.g., `<ol type="a">`, `<ol type="I">`).

This enables more flexible list formatting in Markdown, enhancing the output to match the intended ordering style.

# Usage

```js
import {marked} from "marked";
import {markedMoreLists} from "marked-more-lists";

// or UMD script
// <script src="https://cdn.jsdelivr.net/npm/marked/lib/marked.umd.js"></script>
// <script src="https://cdn.jsdelivr.net/npm/marked-more-lists/lib/index.umd.js"></script>

const options = {};

marked.use(markedMoreLists(options));

const exampleMarkdown = `
1. item 1
2. item 2
	a. item 2a
		I. sub item I
		II. sub item II
	x. item 2x
`;

marked.parse(exampleMarkdown);
// <ol>
//   <li>item 1</li>
//   <li>item 2
//     <ol type="a">
//       <li>item 2a</li>
//       <ol type="I">
//         <li>sub item I</li>
//         <li>sub item II</li>
//       </ol>
//       <li value="24">item 2x</li>
//     </ol>
//   </li>
// </ol>
```

## `options`

_There are no options for this extension._
