# Apple Music to Spotify

Steps:

- Extract from Apple Music
- Find equivalent in Spotify


## Extract

```js
let tracks = []

// Repeat this until you have all the tracks
// do not care about duplictes, we will remove them later
tracks.push(...Array.from(document.querySelectorAll(".library-track.svelte-m5riql")).map(i => {
    return [
        i.children[1].textContent.trim(),
        i.children[2].textContent.trim(),
        ]
}))

// make them unique
uniqueTracks = Array.from(new Set(tracks()))

// Add them back
tracks = []
for (let i = 0; i < uniqueTracks.length; uniqueTracks+=2) {
    newTracks.push([uniqueTracks[i], uniqueTracks[i+1]])
}

console.log(JSON.stringify(tracks))
```

## Find the equivalent in spotify and add it to your library

```bash
pnpm install
pnpm run start
```
