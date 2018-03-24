# Workshop APIs:

 1. Open Github, Go to Settings.

2. Developer Settings.

3. Access Tokens --> Generate Access Token --> Enter your Password --> Choose Access Token Name --> Choose it's Privilages --> Generate Token.

4. Go to [Github API DOCS](https://developer.github.com/v3/), Get the Peices of the Puzzle.
- - HOST: api.github.com
- - PATH: /users/:username/repos
- - PARAMS: access_token
- - METHOD: GET

5. Construct you URL:
https://api.github.com/users/{username}/repos?access_token={accessToken}

6. Code your App:

```javascript

window.onload = gitHupApi;

function fetch(url, callback) {
  var xhr = new XMLHttpRequest();
  xhr.onreadystatechange = function() {
    if (xhr.readyState == 4 && xhr.status == 200) {
      var response = JSON.parse(xhr.responseText);
      callback(response);
    }
  }
  xhr.open('GET', url)
  xhr.send();
}


function gitHupApi () {
  var url = 'https://api.github.com/users/salam-dalloul?access_token=7c2090850cc78c820a238f9f1c772f2540a07c60'
  fetch(url, function (response) {
   var repos = response.repos_url;
   fetch(repos, function (response) {
    var avatar_url = response[0].owner.avatar_url;
    var img = document.getElementById('github-user-avatar');
    img.src = avatar_url;
   })
  })
}

```
