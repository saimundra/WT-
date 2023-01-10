# What is Event Bubbling?
:-Event Bubbling is a concept in the DOM (Document Object Model). It happens when an element receives an event, and that event bubbles up (or you can say is transmitted or propagated) to its parent and ancestor elements in the DOM tree until it gets to the root element.

# Let's look at an example so I can better explain how event bubbling works.

# The HTML:

<body>
  <div>
    <span>
      <button>Click Me!</button>
    </span>
  </div>
</body>

# The CSS:

body {
  padding: 20px;
  background-color: pink;
}

div {
  padding: 20px;
  background-color: green;
  width: max-content;
}

span {
  display: block;
  padding: 20px;
  background-color: blue;
}



# What is event capturing?
:-Event capturing is one of two ways to do event propagation in the HTML DOM. In event capturing, an event propagates from the outermost element to the target element. It is the opposite of event bubbling, where events propagate outwards from the target to the outer elements.

# example
In the example below, we add click event handlers on every HTML element using JavaScript for loop.
# HTML
<html>
  <head></head>
  <body>
    <article id="ancestor" >
      article element
      <div id="parent" >
        div element
        <p id="child" >
          p element
        </p>
      </div>
    </article>
  </body>
</html>

<script>
  // Script to click event handler to capture on each element
  for(let elem of document.querySelectorAll('*')) {
    elem.addEventListener("click", e => console.log("Capturing:", elem.tagName), true);
  }
</script>