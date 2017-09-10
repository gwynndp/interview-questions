Example of the origins of single-page applications based on the '#' and 'hashchange' event listener.

window.addEventListener('hashchange', function () {
  if(window.location.hash === '#/bookmark/1') {
    console.log('Page 1 is cool');
  }
});

window.addEventListener('hashchange', function () {
  if(window.location.hash === '#/bookmark/2') {
    console.log('Page 2 is cool');
  }
});

window.addEventListener('hashchange', function () {
  if(window.location.hash === '#/bookmark/3') {
    console.log('Page 3 is cool');
  }
});

--------------------

# is a page fragment identifier

The #/bookmark/1 looks like an anchor point on the page, or a link to an anchor point.  The anchor doesn't have to be there for the link to exist.  The console can still be made to respond to anchor links, like getting particular content associated with it that doesn't exist on the page but does exist on the server
