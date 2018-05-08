# react-demo

* Code from _7/5_ is on branch: **state-intro**

## TODO

* Fetch data (playlists) from the API
* Display the fetched data
* Update state with fetched data
* Filter state data with an input field

## Vanilla JavaScript reference

_Vanilla JavaScript Reference_

```js
const App = {
  state: {
    playlists: []
  },
  getLatest(){
    fetch('https://folksa.ga/api/playlists?key=flat_eric')
      .then(response => response.json())
      .then((fetchedPlaylists) => {
        this.state.playlists = fetchedPlaylists;
        return fetchedPlaylists;
      })
      .then(this.displayLatest)
  },
  displayLatest(fetchedPlaylists){
    let outputHTML = '';
    for(const playlist of fetchedPlaylists){
      outputHTML += `<div>
        <p>${playlist.title}</p>
      </div>`
    }
  document.body.innerHTML = outputHTML;
  }
}

App.getLatest();

```