# Assignment

Your assignment will be to build your own jQuery library through a series of different steps. This will help you learn JavaScript concepts.
All tasks are jQuery equivalent methods.

To be clear, you cannot use jQuery. You must use standard JavaScript methods to create **jQuery equivalent methods**.

## Instructions

First we will want to run the project.
This can be done by running in the project root:

`yarn`

and then

`yarn start`

This will start a local server on port 3000.
[Navigate to it](http://localhost:3000).
From here you can access all the test runners from one place.

Next you should open the project folder (or just the learnQuery folder) in the code editor.

In the learnQuery folder you will find the assignments.

For each task there is a spec and src folder. The runner.html is the test runner you can get to by going to the localhost server.

Before starting any task first read the Readme section for it, then open the files in the spec and src folders.

You can use the spec file to see the test criteria your code needs to pass. DO NOT MODIFY THIS FILE.

Everything you code goes in the src folder .js file. Keep all your code in the `// code goes here` function.

The task is considered complete when all the tests are passing.

Every task should be completed in order. Do not skip ahead, as tasks build upon one another.

If you are stuck, either because you don't understand what is asked of you or how to do it, please ask your mentor to help you.

The project has eslint and prettier on it, configured to this company's liking. Please consult with your mentor about setting up your editor environment to support this.

Your finished task sholdn't have any warnings or errors from eslint. This does not mean you just prefix everything with eslint ignores, ask your mentor if you cannot figure out why something is a warning.

# Tasks

Helpful references:

- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

## 0. Example

You need to write a function that computes n-th Fibonacci number.

The code can be found in repository /00.example/src.

Also, specs for this task can be found in /00.example/spec.

_This is an example task to show you how the specs and src work._

## 1. Simple Selector function

Terms:

- Selector - selects which elements in the DOM to work with.

References:

- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors)
- [Minimal sizzle selector](http://sizzlejs.com/)

Description:

- Can select elements based on one of three items:

  - the given tag name
  - class name
  - or ID

- Should return an array of selected HTML elements

Examples:

```JavaScript
domSelector('#some-id');
domSelector('.some-class');
domSelector('some-tag');
```

## 2. CSS manipulation

Terms:

- CSS (cascading style sheets) is a stylesheet language used to describe the presentation of a document written in HTML or XML

References:

- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/CSS)

Description:

- Should be able to set/change single or multiple CSS property values for selected elements, and also get the value of any existing CSS property

Examples:

```JavaScript
// set single property
cssProp(htmlElement, cssProperty, value);

// set multiple properties
cssProp(htmlElement, {cssProperty: value, cssProperty: value});

// get CSS property value
cssProp(htmlElement, cssProperty);
```

## 3. CSS class manipulation

Terms:

- CSS class selectors match an element based on the contents of the element's class attribute, one of which must match exactly the class name given

References:

- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/CSS/Class_selectors)

Description:

- Should either add, remove, or toggle a named Class to the matched element(s), or else determine if that element is assigned that named class

Examples:

```JavaScript
cssClass.add(htmlElement, className);
cssClass.remove(htmlElement, className);
cssClass.toggle(htmlElement, className);
cssClass.has(htmlElement, className);
```

## 4. DOM manipulation

Terms:

- "The Document Object Model (DOM) is a programming interface for HTML, XML and SVG documents. It provides a structured representation of the document (a tree) and it defines a way that the structure can be accessed from programs so that they can change the document structure, style and content."

References:

- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/API/)Document_Object_Model

Description:

- Should manipulate the DOM in the specified manner:
  - remove an element
  - append an element to the DOM
  - insert an element in the DOM after a specified element
  - insert an element in the DOM before a specified element
  - get the value of a selected element

Examples:

```JavaScript
dom.remove(element);
dom.append(targetElement, element);
dom.after(targetElement, element);
dom.prepend(targetElement, element);
dom.before(targetElement, element);
dom.val(targetElement);
```

## 5. Ajax request function

Terms:

- Ajax stands for Asynchronous JavaScript and XML. It is a model, combining multiple technologies so web applications are able to make quick, incremental updates to the user interface without reloading the entire browser page
- All data is sent as JSON

References:

- [Mozilla Developer Network](https://developer.mozilla.org/en/docs/AJAX)

Description:

- should make a successful Ajax request and post
- should call a custom function on either success or failure (with a custom context)
- should call a custom function when a request is completed (with a custom context)

Examples:

```JavaScript
ajaxReq(url, options);

ajaxReq(url, {
  method: 'POST',
  data: {},
  context: this,
  failure: function() {},
  success: function() {},
  complete: function() {}
});
```

## 6. Event Listeners

Terms:

- Event Listeners attach event handlers to elements and listen for specified events. They specify what to do when specific events register on those elements

References:

- [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/API/EventTarget.addEventListener)

Description:

- should register listeners for single or multiple events on the specified element and apply a callback
- should be able to remove listener callbacks from specified elements

Examples:

```JavaScript
eventListener.on(element, event, callback);

// removes a specific callback on an element of the event type
eventListener.off(element, event, callback);

// removes all callbacks on an element of the event type
eventListener.off(element, event);

// removes all callbacks on an element
eventListener.off(element);
```

### 6.1. Additional Event Listener trigger

Description:

- Should trigger a specific event on a selected element

Example:

    eventListener.trigger(element, event);

### 6.2. Event delegation

Description:

- Delegate a specific event to an element with the specified class name

Example:

```JavaScript
eventListener
  .delegate(monitoredElement, className, event, callback);
```

## 7. Make learnQuery!

Create your own learnQuery library using the knowledge gained from making the previous functions. It should include all the functions you created in the previous tasks, and it should look and function similar to jQuery.

You have already created the functionality in the previous tasks. Now you simply need to provide a way to implement them.

Your solution **must** support **chaining**!

**Hint**: Pay attention to scope, closures, and context.

Example:

```JavaScript
learnQuery('.thisClass')
  .on('click', callback)
  .removeClass('thisClass')
  .addClass('anotherClass');
```

# FAQ

- What "affix()" does?

Affix accepts CSS selectors as arguments and adds those elements to the DOM.
Details: https://github.com/searls/jasmine-fixture

# License

LearnQuery is released under the [MIT license](http://www.opensource.org/licenses/MIT).
