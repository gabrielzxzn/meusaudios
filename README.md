<html><head>
  <meta charset="UTF-8">
  <title>Áudio</title>
  <link rel="stylesheet" href="https://cdn.plyr.io/3.6.7/plyr.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;700&display=swap');
      
    body {
      height: 100vh;
      overflow: hidden;
      margin: 0px;
    }    

    .audio-container {
      display: flex;
      align-items: center;
      justify-content: space-between;
      font-family: 'Open Sans', sans-serif;
      justify-content: flex-start;
      cursor: pointer; 
      width: 100px;
    }

    .audio-container img {
      width: 50px;
      height: 50px;
      border-radius: 50%;
      object-fit: cover;
      padding-right: 8px;
      padding-left: 10px;
    }

    .audio-container .microphone-icon {
      position: relative;
      margin-left: -67px;
      margin-bottom: -25px;
      font-size: 22px;
      color: #4ad954;
    }

    .audio-container .microphone-icon.blue {
      color: #3db8ee;
    }

    .plyr--audio .plyr__control.plyr__tab-focus,
    .plyr--audio .plyr__control:hover,
    .plyr--audio .plyr__control[aria-expanded=false] {
      background: rgba(0, 0, 0, 0);
      background: var(--plyr-audio-control-background-hover, var(--plyr-color-main, var(--plyr-color-main, rgba(0, 0, 0, 0))));
      color: rgba(0, 0, 0, 0);
      color: var(--plyr-audio-control-color-hover, #797979)
    }

    .plyr--audio .plyr__controls {
      background: rgba(0, 0, 0, 0);
      background: var(--plyr-audio-controls-background, rgba(0, 0, 0, 0));
      border-radius: inherit;
      color: #4a5464;
      color: var(--plyr-audio-control-color,#4a5464);
      margin-left: 0px;
      padding: 0px;
    }

    .plyr--audio .plyr__control--overlaid .plyr__control__icon {
      font-size: 33px;
    }

    .plyr--full-ui input[type=range]::-webkit-slider-thumb {
      -webkit-appearance: none;
      border: 0;
      border-radius: 100%;
      box-shadow: 0 1px 1px rgba(35,40,47,.15),0 0 0 1px rgba(35,40,47,.2);
      box-shadow: var(--plyr-range-thumb-shadow,0 1px 1px rgba(35,40,47,.15),0 0 0 1px rgba(35,40,47,.2));
      height: 13px;
      height: var(--plyr-range-thumb-height,13px);
      margin-top: -4px;
      margin-top: calc(var(--plyr-range-thumb-height,13px)/2*-1 - var(--plyr-range-track-height,5px)/2*-1);
      position: relative;
      -webkit-transition: all .2s ease;
      transition: all .2s ease;
      width: 13px;
      width: var(--plyr-range-thumb-height,13px);
      background: var(--range-thumb-background, #4ad954);
    }  

    .plyr--full-ui input[type=range].blue::-webkit-slider-thumb {
      background: var(--range-thumb-background-active, #3db8ee);
    }
  
    .hide {
      display: none;
    }

    .plyr__controls .plyr__controls__item.plyr__progress__container:first-child,
    .plyr__controls .plyr__controls__item.plyr__time+.plyr__time,
    .plyr__controls .plyr__controls__item.plyr__time:first-child {
      padding-left: 0;
      display: block;
      margin-left: 7.5px;
    }

    .plyr__time+.plyr__time:before {
      content: "";
      margin-right: var(--plyr-control-spacing);
    }

    .plyr--audio .plyr__controls .plyr__controls__item.plyr__time--current.hide,
    .plyr--audio .plyr__controls .plyr__controls__item.plyr__time--duration.hide {
      display: none;
    }

  </style>
</head>
<body><div hidden="" id="sprite-plyr"><!--?xml version="1.0" encoding="UTF-8"?--><svg xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"><symbol id="plyr-airplay" viewBox="0 0 18 18"><path d="M16 1H2a1 1 0 00-1 1v10a1 1 0 001 1h3v-2H3V3h12v8h-2v2h3a1 1 0 001-1V2a1 1 0 00-1-1z"></path><path d="M4 17h10l-5-6z"></path></symbol><symbol id="plyr-captions-off" viewBox="0 0 18 18"><path d="M1 1c-.6 0-1 .4-1 1v11c0 .6.4 1 1 1h4.6l2.7 2.7c.2.2.4.3.7.3.3 0 .5-.1.7-.3l2.7-2.7H17c.6 0 1-.4 1-1V2c0-.6-.4-1-1-1H1zm4.52 10.15c1.99 0 3.01-1.32 3.28-2.41l-1.29-.39c-.19.66-.78 1.45-1.99 1.45-1.14 0-2.2-.83-2.2-2.34 0-1.61 1.12-2.37 2.18-2.37 1.23 0 1.78.75 1.95 1.43l1.3-.41C8.47 4.96 7.46 3.76 5.5 3.76c-1.9 0-3.61 1.44-3.61 3.7 0 2.26 1.65 3.69 3.63 3.69zm7.57 0c1.99 0 3.01-1.32 3.28-2.41l-1.29-.39c-.19.66-.78 1.45-1.99 1.45-1.14 0-2.2-.83-2.2-2.34 0-1.61 1.12-2.37 2.18-2.37 1.23 0 1.78.75 1.95 1.43l1.3-.41c-.28-1.15-1.29-2.35-3.25-2.35-1.9 0-3.61 1.44-3.61 3.7 0 2.26 1.65 3.69 3.63 3.69z" fill-rule="evenodd" fill-opacity=".5"></path></symbol><symbol id="plyr-captions-on" viewBox="0 0 18 18"><path d="M1 1c-.6 0-1 .4-1 1v11c0 .6.4 1 1 1h4.6l2.7 2.7c.2.2.4.3.7.3.3 0 .5-.1.7-.3l2.7-2.7H17c.6 0 1-.4 1-1V2c0-.6-.4-1-1-1H1zm4.52 10.15c1.99 0 3.01-1.32 3.28-2.41l-1.29-.39c-.19.66-.78 1.45-1.99 1.45-1.14 0-2.2-.83-2.2-2.34 0-1.61 1.12-2.37 2.18-2.37 1.23 0 1.78.75 1.95 1.43l1.3-.41C8.47 4.96 7.46 3.76 5.5 3.76c-1.9 0-3.61 1.44-3.61 3.7 0 2.26 1.65 3.69 3.63 3.69zm7.57 0c1.99 0 3.01-1.32 3.28-2.41l-1.29-.39c-.19.66-.78 1.45-1.99 1.45-1.14 0-2.2-.83-2.2-2.34 0-1.61 1.12-2.37 2.18-2.37 1.23 0 1.78.75 1.95 1.43l1.3-.41c-.28-1.15-1.29-2.35-3.25-2.35-1.9 0-3.61 1.44-3.61 3.7 0 2.26 1.65 3.69 3.63 3.69z" fill-rule="evenodd"></path></symbol><symbol id="plyr-download" viewBox="0 0 18 18"><path d="M9 13c.3 0 .5-.1.7-.3L15.4 7 14 5.6l-4 4V1H8v8.6l-4-4L2.6 7l5.7 5.7c.2.2.4.3.7.3zm-7 2h14v2H2z"></path></symbol><symbol id="plyr-enter-fullscreen" viewBox="0 0 18 18"><path d="M10 3h3.6l-4 4L11 8.4l4-4V8h2V1h-7zM7 9.6l-4 4V10H1v7h7v-2H4.4l4-4z"></path></symbol><symbol id="plyr-exit-fullscreen" viewBox="0 0 18 18"><path d="M1 12h3.6l-4 4L2 17.4l4-4V17h2v-7H1zM16 .6l-4 4V1h-2v7h7V6h-3.6l4-4z"></path></symbol><symbol id="plyr-fast-forward" viewBox="0 0 18 18"><path d="M7.875 7.171L0 1v16l7.875-6.171V17L18 9 7.875 1z"></path></symbol><symbol id="plyr-logo-vimeo" viewBox="0 0 18 18"><path d="M17 5.3c-.1 1.6-1.2 3.7-3.3 6.4-2.2 2.8-4 4.2-5.5 4.2-.9 0-1.7-.9-2.4-2.6C5 10.9 4.4 6 3 6c-.1 0-.5.3-1.2.8l-.8-1c.8-.7 3.5-3.4 4.7-3.5 1.2-.1 2 .7 2.3 2.5.3 2 .8 6.1 1.8 6.1.9 0 2.5-3.4 2.6-4 .1-.9-.3-1.9-2.3-1.1.8-2.6 2.3-3.8 4.5-3.8 1.7.1 2.5 1.2 2.4 3.3z"></path></symbol><symbol id="plyr-logo-youtube" viewBox="0 0 18 18"><path d="M16.8 5.8c-.2-1.3-.8-2.2-2.2-2.4C12.4 3 9 3 9 3s-3.4 0-5.6.4C2 3.6 1.3 4.5 1.2 5.8 1 7.1 1 9 1 9s0 1.9.2 3.2c.2 1.3.8 2.2 2.2 2.4C5.6 15 9 15 9 15s3.4 0 5.6-.4c1.4-.3 2-1.1 2.2-2.4.2-1.3.2-3.2.2-3.2s0-1.9-.2-3.2zM7 12V6l5 3-5 3z"></path></symbol><symbol id="plyr-muted" viewBox="0 0 18 18"><path d="M12.4 12.5l2.1-2.1 2.1 2.1 1.4-1.4L15.9 9 18 6.9l-1.4-1.4-2.1 2.1-2.1-2.1L11 6.9 13.1 9 11 11.1zM3.786 6.008H.714C.286 6.008 0 6.31 0 6.76v4.512c0 .452.286.752.714.752h3.072l4.071 3.858c.5.3 1.143 0 1.143-.602V2.752c0-.601-.643-.977-1.143-.601L3.786 6.008z"></path></symbol><symbol id="plyr-pause" viewBox="0 0 18 18"><path d="M6 1H3c-.6 0-1 .4-1 1v14c0 .6.4 1 1 1h3c.6 0 1-.4 1-1V2c0-.6-.4-1-1-1zm6 0c-.6 0-1 .4-1 1v14c0 .6.4 1 1 1h3c.6 0 1-.4 1-1V2c0-.6-.4-1-1-1h-3z"></path></symbol><symbol id="plyr-pip" viewBox="0 0 18 18"><path d="M13.293 3.293L7.022 9.564l1.414 1.414 6.271-6.271L17 7V1h-6z"></path><path d="M13 15H3V5h5V3H2a1 1 0 00-1 1v12a1 1 0 001 1h12a1 1 0 001-1v-6h-2v5z"></path></symbol><symbol id="plyr-play" viewBox="0 0 18 18"><path d="M15.562 8.1L3.87.225c-.818-.562-1.87 0-1.87.9v15.75c0 .9 1.052 1.462 1.87.9L15.563 9.9c.584-.45.584-1.35 0-1.8z"></path></symbol><symbol id="plyr-restart" viewBox="0 0 18 18"><path d="M9.7 1.2l.7 6.4 2.1-2.1c1.9 1.9 1.9 5.1 0 7-.9 1-2.2 1.5-3.5 1.5-1.3 0-2.6-.5-3.5-1.5-1.9-1.9-1.9-5.1 0-7 .6-.6 1.4-1.1 2.3-1.3l-.6-1.9C6 2.6 4.9 3.2 4 4.1 1.3 6.8 1.3 11.2 4 14c1.3 1.3 3.1 2 4.9 2 1.9 0 3.6-.7 4.9-2 2.7-2.7 2.7-7.1 0-9.9L16 1.9l-6.3-.7z"></path></symbol><symbol id="plyr-rewind" viewBox="0 0 18 18"><path d="M10.125 1L0 9l10.125 8v-6.171L18 17V1l-7.875 6.171z"></path></symbol><symbol id="plyr-settings" viewBox="0 0 18 18"><path d="M16.135 7.784a2 2 0 01-1.23-2.969c.322-.536.225-.998-.094-1.316l-.31-.31c-.318-.318-.78-.415-1.316-.094a2 2 0 01-2.969-1.23C10.065 1.258 9.669 1 9.219 1h-.438c-.45 0-.845.258-.997.865a2 2 0 01-2.969 1.23c-.536-.322-.999-.225-1.317.093l-.31.31c-.318.318-.415.781-.093 1.317a2 2 0 01-1.23 2.969C1.26 7.935 1 8.33 1 8.781v.438c0 .45.258.845.865.997a2 2 0 011.23 2.969c-.322.536-.225.998.094 1.316l.31.31c.319.319.782.415 1.316.094a2 2 0 012.969 1.23c.151.607.547.865.997.865h.438c.45 0 .845-.258.997-.865a2 2 0 012.969-1.23c.535.321.997.225 1.316-.094l.31-.31c.318-.318.415-.781.094-1.316a2 2 0 011.23-2.969c.607-.151.865-.547.865-.997v-.438c0-.451-.26-.846-.865-.997zM9 12a3 3 0 110-6 3 3 0 010 6z"></path></symbol><symbol id="plyr-volume" viewBox="0 0 18 18"><path d="M15.6 3.3c-.4-.4-1-.4-1.4 0-.4.4-.4 1 0 1.4C15.4 5.9 16 7.4 16 9c0 1.6-.6 3.1-1.8 4.3-.4.4-.4 1 0 1.4.2.2.5.3.7.3.3 0 .5-.1.7-.3C17.1 13.2 18 11.2 18 9s-.9-4.2-2.4-5.7z"></path><path d="M11.282 5.282a.909.909 0 000 1.316c.735.735.995 1.458.995 2.402 0 .936-.425 1.917-.995 2.487a.909.909 0 000 1.316c.145.145.636.262 1.018.156a.725.725 0 00.298-.156C13.773 11.733 14.13 10.16 14.13 9c0-.17-.002-.34-.011-.51-.053-.992-.319-2.005-1.522-3.208a.909.909 0 00-1.316 0zm-7.496.726H.714C.286 6.008 0 6.31 0 6.76v4.512c0 .452.286.752.714.752h3.072l4.071 3.858c.5.3 1.143 0 1.143-.602V2.752c0-.601-.643-.977-1.143-.601L3.786 6.008z"></path></symbol></svg></div>
  <div class="audio-container" id="audioContainer">
    <!-- Cole o link do Seu áudio Abaixo-->
    <div tabindex="0" class="plyr plyr--full-ui plyr--audio plyr--html5 blue plyr--paused" style="--range-thumb-background: #3db8ee;"><div class="plyr__controls"><button class="plyr__controls__item plyr__control" type="button" data-plyr="play" aria-label="Play"><svg class="icon--pressed" aria-hidden="true" focusable="false"><use xlink:href="#plyr-pause"></use></svg><svg class="icon--not-pressed" aria-hidden="true" focusable="false"><use xlink:href="#plyr-play"></use></svg><span class="label--pressed plyr__sr-only">Pause</span><span class="label--not-pressed plyr__sr-only">Play</span></button><div class="plyr__controls__item plyr__progress__container"><div class="plyr__progress"><input data-plyr="seek" type="range" min="0" max="100" step="0.01" value="0" autocomplete="off" role="slider" aria-label="Seek" aria-valuemin="0" aria-valuemax="16.222" aria-valuenow="2.840382" id="plyr-seek-3125" aria-valuetext="00:02 of 00:16" style="--value: 17.51%;" seek-value="-3.3542976939203357"><progress class="plyr__progress__buffer" min="0" max="100" value="100" role="progressbar" aria-hidden="true">% buffered</progress><span class="plyr__tooltip" style="left: 0%;">00:00</span></div></div><div class="plyr__controls__item plyr__time--current plyr__time hide" aria-label="Current time">00:02</div><div class="plyr__controls__item plyr__time--duration plyr__time" aria-label="Duration">00:07</div></div><audio class="plyr" src="https://midias-s3-global.sendbot.cloud/sendbot/public/workspaces/cm2fopiec0007j1th2pbzb3ug/typebots/cm39bdwy70003v41c3aieg8cq/blocks/thtceyv0slpsp4lcxwjxhy7m?v=1731208301670"></audio></div>
    <!-- Cole o link da Sua imagem Abaixo-->
    <img src="https://midias-s3-global.sendbot.cloud/sendbot/public/workspaces/cm2fopiec0007j1th2pbzb3ug/typebots/cm39bdwy70003v41c3aieg8cq/hostAvatar?v=1731106152265" alt="Imagem">
    <div class="microphone-icon blue">
      <i class="fas fa-microphone"></i>
    </div>
  </div>
  
  <script src="https://cdn.plyr.io/3.6.7/plyr.js"></script>
  <script>
    document.addEventListener('DOMContentLoaded', function() {
      const player = new Plyr('.plyr', {
        controls: ['play', 'progress', 'current-time', 'duration']
      });

      const audioElement = document.querySelector('.plyr');
      const currentTimeElement = document.querySelector('.plyr__time--current');
      const durationElement = document.querySelector('.plyr__time--duration');
      const microphoneIcon = document.querySelector('.microphone-icon');

      currentTimeElement.classList.add('hide'); // Adiciona a classe 'hide' ao iniciar

      audioElement.addEventListener('play', function() {
        currentTimeElement.classList.remove('hide');
        durationElement.classList.add('hide');
        microphoneIcon.classList.add('blue'); // Adiciona a classe 'blue' para alterar a cor do ícone
        audioElement.classList.add('blue'); // Adiciona a classe 'blue' para alterar o background do controle deslizante
        audioElement.style.setProperty('--range-thumb-background', '#3db8ee');
      });

      audioElement.addEventListener('pause', function() {
        currentTimeElement.classList.add('hide');
        durationElement.classList.remove('hide');
      });

      const audioContainer = document.getElementById('audioContainer');
      audioContainer.addEventListener('click', function() {
        const playButton = audioContainer.querySelector('.plyr__controls button[data-plyr="play"]');
        playButton.click();
      });

      const playPauseButton = document.getElementById('audioContainer').querySelector('.plyr__controls button[data-plyr="play"]');
      const audioBox = document.querySelector('.audio-box');
      playPauseButton.addEventListener('click', function() {
        const playButton = audioContainer.querySelector('.plyr__controls button[data-plyr="play"]');
        playButton.click();
      });

      audioBox.addEventListener('click', function(event) {
        event.stopPropagation(); 
        const playButton = audioContainer.querySelector('.plyr__controls button[data-plyr="play"]');
        playButton.click();
      });
    });
  </script>


</body></html>
