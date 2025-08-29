# Programming Hero Assignment 05 
1. What is the difference between getElementById, getElementsByClassName, and querySelector / querySelectorAll? 

  Answer: getElementById( ) : We use this when we want to grab a single element by its id. Since an id is supposed to be unique, it either gives us that one element or null if it doesn't exist.

  getElementsByClassName( ) : This is for when multiple elements share the same class. It returns something like a list (called an HTMLCollection). It's not a real array, so if we want to work with each element, we usually loop through it.

  querySelector( ) : This one works just like CSS selectors. It gives us the first element that matches the selector we write, like .class, #id, or even div p.

  querySelectorAll( ) : Same idea as querySelector, but instead of stopping at the first match, it gives us all the matching elements in a NodeList, which we can loop through easily with forEach.


2. How do you create and insert a new element into the DOM?

  Answer:If we want to add something new like a div, paragraph, or button to our webpage using JavaScript, the steps are simple:
  First, we create the element:

  const newDiv = document.createElement("div");

  Here we made a 'newDiv' but it’s not on the page yet it’s just created in memory. Then we add some content or styling to it,

  newDiv.innerText = "Hello World!";
  newDiv.className = "greeting";

  This way, the div will show "Hello World!" and also have a class called greeting. Finally, we put it into the page (the DOM)

  document.body.appendChild(newDiv);

3. What is Event Bubbling and how does it work?

  Answer: Event Bubbling happens when an event we trigger on an element, like clicking a button, doesn’t just stay there it "bubbles up" through its parent elements. So the browser first handles the event on the element we clicked, then on its parent, then the parent’s parent, and so on, all the way up to the document.

  Example:
  If we click a 'button' inside a 'div', the click first affects the button itself, then the 'div' around it, then maybe the 'body' and 'html'. It’s like the click travels upward through all the container elements.

4. What is Event Delegation in JavaScript? Why is it useful?

  Answer: Event Delegation in JavaScript means we put a single event listener on a parent element instead of adding separate listeners to each child. Because events bubble up, the parent can catch events from its children and decide what to do.

  Example:
  Instead of adding click listeners to 100 li items, we can just add one listener on the 'ul' and check which 'li' was clicked using event.target.

  It's useful because:

  i) Saves memory and makes the page run faster.

  ii) Works automatically for elements we add later, even after the page loads.

5. What is the difference between preventDefault() and stopPropagation() methods?

  Answer: preventDefault(): This stops the browser from doing what it normally does.
  Example: Clicking a link usually takes us to a new page. If we use event.preventDefault(), the link won't go anywhere.
  stopPropagation(): This stops the event from moving up to parent elements.
  Example: If we click a button inside a 'div', only the button's click handler runs. The 'div' won’t respond to that click.