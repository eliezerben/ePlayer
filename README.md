# ePlayer
## Index
- [About](#about)
- [Usage](#usage)
- [Player Options](#player-options)
- [To do](#to-do)  
## About
**ePlayer** is an easy to use audio player library which can be used to add custom full-fledged audio players to websites.  
It supports all essential features such as:
- Playlists
- Play / Pause
- Repeat
- Shuffle
- Previous song
- Next song
- Volume control
- Ability to add more than one player to the same page.

[Click here](http://eliezer.co.in/ePlayer) to open a demo page which uses this audio player.  
The code for the demo is available in the [/example](https://github.com/eliezerben/ePlayer/tree/master/example) directory.

## Usage
To try out **ePlayer** on your webpage, do the following:
1. Clone this repository and copy the content to your project directory.
2. Include the following `js` and `css` files in the `<head>` section of your html page.  
    ```
    <head>
    ...
    <script src='eSlider.js'></script>
    <script src='ePlayer.js'></script>
    <script src='darkTheme.js'></script>
    <link type='text/css' rel='stylesheet' href='darktheme.css'>
    ....
    </head>
    ```
4. To add a player to the page, paste the following html snippet.  
    The snippet contains html elements representing the different controls of the player which can be rearranged as needed.  
    Notice the id of the player `id='p1'` which will be used later.  
    _**Note:** The player will be enhanced in the future to eliminate this step._
    ```
    <div id='p1' class='ep-dt-container'>
        <div data-ep-role='controls' class='ep-dt-controls'>
            <div data-ep-role='fastRewind' class='ep-dt-controlIcon ep-dt-fastRewind'></div>
            <div data-ep-role='play' class='ep-dt-controlIcon ep-dt-play'></div>
            <div data-ep-role='fastForward' class='ep-dt-controlIcon ep-dt-fastForward'></div>
            <p data-ep-role='curTime' class='ep-dt-curTime'>00:00</p>
            <div data-ep-role='seekSlider' class='ep-dt-seekSlider'>
                <div data-ep-role='seekComp' class='ep-dt-seekComp'></div>
                <div data-ep-role='seekTrack' class='ep-dt-seekTrack'></div>
            </div>
            <p data-ep-role=totTime class='ep-dt-totTime'>00:00</p>
            <div data-ep-role='repeat' class='ep-dt-controlIcon ep-dt-repeatOff'></div>
            <div data-ep-role='shuffle' class='ep-dt-controlIcon ep-dt-shuffleOff'></div>
            <div data-ep-role='volume' class='ep-dt-controlIcon ep-dt-volumeFull'></div>
            <div data-ep-role='volSlider' class='ep-dt-volSlider'>
                <div data-ep-role='volComp' class='ep-dt-volComp'></div>
                <div data-ep-role='volTrack' class='ep-dt-volTrack'></div>
            </div>
        </div>
        <ol data-ep-role='playlist' class='ep-dt-playlist'></ol>
    </div>
    ```
5. Configure the player by creating an `ePlayer` instance and providing initial options if needed.  
   It is recommended to add the code to the end of the html file.
   Example code to initialize the player:
   ```
   const player = ePlayer.darkTheme(
       // Id of player specified in the player's HTML code
       'p2',
       // Initial settings of the player
       {
           playlist: true,
           repeat: 'off',
           volume: 0.5,
       },
       // Playlist items
       [
           { url: <audio 1 url>, name: <audio 1 name> },
           { url: <audio 2 url>, name: <audio 2 name> },
           ...
       ]
   );
   ```
   **Note:** `darkTheme` is a theme of the player. Currently, there are no other themes available.  
   The different initialization options are available in the **[Player Options](#player-options)** section.

## Player Options
The player should be initialized by creating an `ePlayer` object by calling `ePlyaer.<theme>()`. For example:  
```const player = ePlayer.darkTheme(<player-id>, <initialization-options>, <playlist>);```  
_**Note:** The player includes only the theme `darkTheme` by default currently._
- `<player-id>` is the id of the player specified in the html code of the player
- `<initialization-options>` takes the following format:
  ```
  {
      repeat: <"on", "off", "one">,
      shuffle: <"on", "off">,
      volume: Number (0.0 <= volume <= 1.0),
      preload: bool,
      autoplay: bool,
  }
  ```
- `<playlist>` should be an array in the following format:
  ```
  [
      { url: <audio 1 url>, name: <audio 1 name> },
      { url: <audio 2 url>, name: <audio 2 name> },
      ...
  ]
  ```

## To do
- Eliminate the need to provide the html code of the player manually. Instead automatically inject the code using JavaScript.
- Make it easier to add new themes to the player.
