#### HTML Questions:

* What does a `doctype` do?
  - `<!DOCTYPE>` informs the browser which version of HTML is being used. Doctype is a declaration, not a tag.
  - src - https://developer.mozilla.org/en-US/docs/Glossary/Doctype
* What's the difference between standards mode and quirks mode?
  - quirks mode, layout emulates nonstandard behavior in Navigator 4 and Internet Explorer 5 for Windows that is required not to break existing content on the Web. 
  - full standards mode, the behavior is (hopefully) the behavior described by the HTML and CSS specifications. 
  - almost standards mode, there are only a very small number of quirks implemented.
  - src - https://developer.mozilla.org/en-US/docs/Quirks_Mode_and_Standards_Mode
* What's the difference between HTML and XHTML?
  - XHTML is XML
  - src - https://developer.mozilla.org/en-US/docs/Properly_Using_CSS_and_JavaScript_in_XHTML_Documents
* Are there any problems with serving pages as `application/xhtml+xml`?
  - up to and including version 8, Internet Explorer doesn't support files served as XML
  - src - http://www.w3.org/International/articles/serving-xhtml/
* How do you serve a page with content in multiple languages?
  - Always use a language attribute on the html element. This is inherited by all other elements, and so will set a default language for the text in the document head element.
  - create metadata that describes the language of the intended audience of a page, rather than the language of a specific range of text, do so by getting the server to send the information in the HTTP Content-Language header.
  - src - http://www.w3.org/International/questions/qa-html-language-declarations
* What kind of things must you be wary of when design or developing for multilingual sites?
  - Text In Images Won’t Scale
  - Restrictive Word / Sentence length
  - How Colors Are Perceived Across Different Cultures
  - Completely remove text content from templates.
  - Formatting Dates
  - src - http://www.quora.com/What-kind-of-things-one-should-be-wary-of-when-designing-or-developing-for-multilingual-sites
* What are `data-` attributes good for?
  -  data-* attributes allow us to store extra information on standard, semantic HTML elements without other hacks such as classList, non-standard attributes, extra properties on DOM, or setUserData.
  -  src - https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_data_attributes
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
  - Semantics: allowing you to describe more precisely what your content is.
  - Connectivity: allowing you to communicate with the server in new and innovative ways.
  - Offline & Storage: allowing webpages to store data on the client-side locally and operate offline more efficiently.
  - Multimedia: making video and audio first-class citizens in the Open Web.
  - 2D/3D Graphics & Effects: allowing a much more diverse range of presentation options.
  - Performance & Integration: providing greater speed optimization and better usage of computer hardware.
  - Device Access: allowing for the usage of various input and output devices.
  - Styling: letting authors write more sophisticated themes.
  - src - https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/HTML5
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
  - exhaustive answer, see source
  - src - http://stackoverflow.com/questions/19867599/what-is-the-difference-between-localstorage-sessionstorage-session-and-cookie
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
  - `<script>` Parsing of the HTML code pauses while the script is executing. 
  -  `<script async>` Asynchronous is the best of both worlds: HTML parsing may continue and the script will be executed as soon as it’s ready.
  -  `<script defer>` delaying script execution until the HTML parser has finished. A positive effect of this attribute is that the DOM will be available for your script.
  -  src - http://www.quora.com/What-is-the-difference-between-DEFER-and-ASYNC-attributes-on-a-resource-in-html
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
  - 'Move CSS to head' seeks to reduce the number of times the browser must re-flow the document by ensuring that the CSS styles are all parsed in the head, before any body elements are introduced.
  - 'Move CSS Above Scripts' seeks to make sure scripts do not block the loading of CSS resources.
  - 
  - src - https://developers.google.com/speed/pagespeed/module/filter-css-to-head
* What is progressive rendering?
