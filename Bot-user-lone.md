LCS.Interface.getLineGroupMemberList(function(data) {
  var total = data.title;
  var start = data.start;
  var display = data.display;
  // Do something...
  var contacts = data.contacts;
  for (var i = 0; i < contacts.length; i++) {
    var mid = contacts[i].id;
    var displayName = contacts[i].displayName;
    var statusMessage = contacts[i].statusMessage;
    // Do something...
  }
}, function() {
  // Do something for this error...
}, {
  id: "u12345abcde...",
  sort: "asc",
  start: 1,
  display: 70
});