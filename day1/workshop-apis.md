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
//CODE!


```
