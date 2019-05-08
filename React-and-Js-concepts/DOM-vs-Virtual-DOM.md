DOM (Document Object Model):- an abstraction of a structured text. For web developers, this text is an HTML code, and the DOM is simply called HTML DOM. Elements of HTML become nodes in the DOM.

So, while HTML is a text, the DOM is an in-memory representation of this text.

The HTML DOM provides an interface (API) to traverse and modify the nodes. It contains methods like getElementById or removeChild. We usually use JavaScript language to work with the DOM, because… Well, nobody knows why :).

So, whenever we want to dynamicly change the content of the web page, we modify the DOM:

var item = document.getElementById("myLI");
item.parentNode.removeChild(item);

document is an abstraction of the root node, while getElementById, parentNode and removeChild are methods from HTML DOM API.

Well, what are the Issues with DOM:-

The HTML DOM is always tree-structured - which is allowed by the structure of HTML document. This is cool because we can traverse trees fairly easily. Unfortunately, easily doesn’t mean quickly here.

The DOM trees are huge nowadays. Since we are more and more pushed towards dynamic web apps (SPAs), we need to modify the DOM tree incessantly and a lot. And this is a real performance and development pain.

Consider a DOM made of thousands of divs. Remember, we are modern web developers, our app is very SPA! We have lots of methods that handle events - clicks, submits, type-ins… A typical jQuery-like event handler looks like this:

1. find every node interested on an event
2. update it if necessary

But it has two problems:

It’s hard to manage. Imagine that you have to tweak an event handler. If you lost the context, you have to dive really deep into the code to even know what’s going on. Both time-consuming and bug-risky.

It’s inefficient. Do we really need to do all this findings manually? Maybe we can be smarter and tell in advance which nodes are to-be-updated?

Once again, React comes with a helping hand. The solution to problem 1 is declarativeness. Instead of low-level techniques like traversing the DOM tree manually, you simple declare how a component should look like. React does the low-level job for you - the HTML DOM API methods are called under the hood. React doesn’t want you to worry about it - eventually, the component will look like it should.

But this doesn’t solve the performance issue. And this is exactly where the Virtual DOM comes into action.

What the heck is Virtual DOM?:-
First of all - the Virtual DOM was not invented by React, but React uses it and provides it for free.

The Virtual DOM is an abstraction of the HTML DOM. It is lightweight and detached from the browser-specific implementation details. Since the DOM itself was already an abstraction, the virtual DOM is, in fact, an abstraction of an abstraction.

How Virtual DOM works:- 

In summary, here’s what happens when you try to update the DOM in React:

1. The entire virtual DOM gets updated.
2. The virtual DOM gets compared to what it looked like before you updated it. React figures out which objects have changed.
3. The changed objects, and the changed objects only, get updated on the real DOM.
4. Changes on the real DOM cause the screen to change.

Differences:-
1. A virtual DOM object has the same properties as a real DOM object, but it lacks the real thing’s power to directly change what’s on the screen.

2. Manipulating the DOM is slow. Manipulating the virtual DOM is much faster, because nothing gets drawn onscreen. Think of manipulating the virtual DOM as editing a blueprint, as opposed to moving rooms in an actual house.

Summary
Is virtual DOM really the feature to boast on the main page? I would say so. In practise, React performance is absolutely high, and the virtual DOM is surely very helpful here.

