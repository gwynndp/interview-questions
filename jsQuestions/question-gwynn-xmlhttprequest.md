XMLHTTPRequest Object

Used by all modern web browsers.
Below example is for AngularJS... The $scope.$apply statement makes sure the request is made within the AngularJS context, visible to the digest cycle

var someRequest = new XMLHttpRequest();
someRequest.onreadystatechange = function () {
  $scope.$apply(function() {
    if(someRequest.readyState == 4 && someRequest.status == 200) {
      $scope.rules = JSON.parse(someRequest.responseText);
    }
  });
}
someRequest.open("GET", "...url...", true);
someRequest.send();

//object that can go out and make internet requests on it's own
//ajax is a wrapper for it to make it easier to use
