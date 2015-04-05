#### General Questions:

* What did you learn yesterday/this week?
* What excites or interests you about coding?
* What is a recent technical challenge you experienced and how did you solve it?
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
* Talk about your preferred development environment.
* Which version control systems are you familiar with?
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
* Can you describe the difference between progressive enhancement and graceful degradation?
  - **Graceful degradation** Providing an alternative version of your functionality or making the user aware of shortcomings of a product as a safety measure to ensure that the product is usable. 
  - **Progressive enhancement** Starting with a baseline of usable functionality, then increasing the richness of the user experience step by step by testing for support for enhancements before applying them. 
  - src- http://www.w3.org/wiki/Graceful_degradation_versus_progressive_enhancement
* How would you optimize a website's assets/resources?
  - Eliminate unnecessary image resources
  - Leverage CSS3 effects where possible
  - Use web fonts instead of encoding text in images
  - Vector images are ideal for images that consist of geometric shapes
  - Vector images are zoom and resolution-independent
  - SVG files should be minified to reduce their size
  - SVG files should be compressed with GZIP
  - Pay close attention to large assets as they result in high overhead
  - Reduce the number of unnecessary pixels by scaling your images to their display size
  - GZIP performs best on text-based assets: CSS, JavaScript, HTML
  - src - https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/?hl=en
* How many resources will a browser download from a given domain at a time?

  | Browser | Parallel Connections |
  | ------- | --------------------- |
  | IE 10 | 8 |
  | Chrome 23 | 6 |
  | Firefox 17 | 6 |
  | Safari 4 | 4 |
  
  - Reason for limiting the number is so that the server will not be overloaded by small amount of browsers and end up classifying user as DDOS attacker.
  
  * What are the exceptions?
    - Loading pages with many AJAX requests in batches. 
* Name 3 ways to decrease page load (perceived or actual load time).
* If you jumped on a project and they used tabs and you used spaces, what would you do?
* Describe how you would create a simple slideshow page.
* What tools do you use to test your code's performance?
* If you could master one technology this year, what would it be?
* Explain the importance of standards and standards bodies.
* What is Flash of Unstyled Content? How do you avoid FOUC?
* Explain what ARIA and screenreaders are, and how to make a website accessible.
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
