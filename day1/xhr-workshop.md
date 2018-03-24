# XHR Workshop:

## GIHPY ..

### Steps:
1. Signup and Greate an App
2. Get API Key: GIhRwl1OBSFdW6jGmZoG41wsS1NgS2P7
3. Go to DOCS - Get the Search End-Point Data:
- - HOST: api.giphy.com
- - PATH: /v1/gifs/search
- - METHOD: GET
- - PARAMS: q, api_key, limit

4. Build Your URL:
- - http://api.giphy.com/v1/gifs/search?q={searchText}&api_key={apiKey}&limit={limit}

5. Construct the Code: 
``` javascript
const select = (selector) => document.querySelector(selector)

select('.search-btn')
.addEventListener("click", () => {

  const searchText = select('.search-query').value;
  const apiKey = 'GIhRwl1OBSFdW6jGmZoG41wsS1NgS2P7';
  const limit = 10;
  const url = `http://api.giphy.com/v1/gifs/search?q=${searchText}&api_key=${apiKey}&limit=${limit}`;
  const resultsContainer = select('.search-results');

  const xhr = new XMLHttpRequest();

  xhr.onreadystatechange = () => {
    if (xhr.readyState === 4 && xhr.status === 200) {
      const result = JSON.parse(xhr.responseText).data;
      console.log(result);
      Object.values(result).map((gif) => {
        const img = document.createElement('img');
        img.src = gif.images.preview_gif.url;
        resultsContainer.appendChild(img);
      });
    };
  };
  xhr.open("GET", url);
  xhr.send();

});
```
