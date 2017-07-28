Explain event delegation:

"Event delegation refers to the process of using event propagation (bubbling) to handle events at a higher level in the DOM than the element on which the event originated. It allows us to attach a single event listener for elements that exist now or in the future."

Event delegation is the strategy of listening on the parent element for events triggered on their child elements.  This works because events triggered on any element 'bubble up' the DOM to their parent and their parent's parent, etc.  Because the parent elements are notified of events, you can place listeners on them instead of duplicating them for each child.  It also allows for higher DOM elements to have different 'reactions' to the same event.

For example, when a list item is clicked it might change color, but the image in the container next to the list may also change to match it. Event delegation caused the parent and grandparent elements of the list item to be notified of the event and if they had listeners for that even they can trigger other changes in the page.

    // Get the element, add a click listener...
    document.getElementById("parent-list").addEventListener("click", function(e) {
      // e.target is the clicked element!
      // If it was a list item
      if(e.target && e.target.nodeName == "LI") {
        // List item found!  Output the ID!
        console.log("List item ", e.target.id.replace("post-", ""), " was clicked!");
      }
    });

An important part of event delegation is 'matching' the event target element when an event happens and having the event listener on the parent confirm that target before it initiates any action.  E.G. The parent BODY element is the delegate that handles events on behalf of all the child A tags -- it needs to see the A tag as the currentTarget even if what was clicked was the span within the A tag.

The default behavior is for an event to propagate/bubble all the way up to the window and trigger a window refresh.

So, another important part of managing event delegation is to preventDefault or preventPropagation when you don't want to trigger other event listeners or want to prevent the page from refreshing.


    https://davidwalsh.name/event-delegate

    https://javascript.info/event-delegation (tutorial exercises too)

    https://blog.meteor.com/browser-events-bubbling-capturing-and-delegation-14db28e924ae  (discusses history a little)

    https://learn.jquery.com/events/event-delegation/



