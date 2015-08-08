#### CSS Questions:

* What is the difference between classes and ID's in CSS?
  - The ID can be used to identify one element, whereas the Class can be used for multiple elements.
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
  - Normalize.css preserves useful defaults rather than "unstyling" everything
  - Normalize.css corrects some common bugs that are out of scope for reset.css
  - Resets aim to remove all built-in browser styling
* Describe Floats and how they work.
  - Floats (Left & Right) position the element to the side of the container element. 
  - Text and inline elements will wrap around the float object.
* Describe z-index and how stacking context is formed.
  - Z-index allows for objects to be layered on top of onanother based on the greater number.
* What are the various clearing techniques and which is appropriate for what context?
  - overflow: hidden 
  - clearfix
  - clear:both
* Explain CSS sprites, and how you would implement them on a page or site.
  - Allow you to store many images together to allow for fewer DNS requests.
  - You can generate a sprite page with build tools available in npm.
* What are your favourite image replacement techniques and which do you use when?
  - You can use CSS to replicate many icons/fonts/images which load faster.
* How would you approach fixing browser-specific styling issues?
  - First identify the root cause of the problems.
  - Source a solutionto that problem.
  - Cross check that solution to other problems and constraints to ensure it won't cause a break further down the pipeline.
  - Use resources such as caniuse.com to check browser compatibility. Use browser engine prefixes where necessary.
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
  - I have used Neat, Ghost, Skeleton, Bootstrap, Flexbox.
  - I prefer to use Flexbox because it is built into the browser.
  - Where IE constraints exist, falling back to Bootstrap is a good option as it supports older versions of IE than Flexbox.
* Have you used or implemented media queries or mobile specific layouts/CSS?
  - Yes of course. For example, my portfolio site utilizes media queries to format text based on browser width. I also hide certain content on mobile as it isn't visually pleasant on a mobile device. 
* Any familiarity with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors?
  - Advantages: faster to write, more options available, modern tools built on top of them.
  - Disadvantages: There are serveral different types of preprocessors so working with differetn people of projects may require picking up different skillsets like all other parts of development. 
  * Describe what you like and dislike about the CSS preprocessors you have used.
    - I love being able to use nesting, variables, mixins, math, Less & Sass are Turing complete so they are very capable.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
