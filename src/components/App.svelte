<script>
  import Mid from "./Mid.svelte";
  import Bottom from "./Bottom.svelte";
  import sunsvg from "./sunsvg.svelte";
  import "../anim";

  let sun = "../../sun.png";
  let palm = "../../palm.png";
</script>

<style>
  @import url("https://fonts.googleapis.com/css?family=PT+Mono|PT+Sans|PT+Sans+Narrow|Permanent+Marker&display=swap");

  .theapp {
    font-family: "PT Mono", Calibri, sans-serif;
    overflow-y: scroll;
    overflow: scroll;
    height: 100vh;
    scroll-snap-type: y proximity;
  }

  .bloc {
    height: 100vh;
    padding: 1px 60px;
    position: relative;
    transition: padding 0.5s;
  }
  @media only screen and (max-width: 800px) {
    .bloc {
      padding: 10px;
    }
  }
  .first {
    background-image: linear-gradient(#160e18, #530250);
  }
  .sunContainer {
    position: absolute;
    left: 27vw;
    top: 20vh;
    width: 46vw;
    height: 46vh;
    transition: width 0.5s;
  }
  @media only screen and (max-width: 800px) {
    .sunContainer {
      left: 7vw;
      top: 15vh;
      width: 86vw;
    }
  }
  .sun {
    /* background-size: 20vh 20vw; */
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
  }

  .first__palm {
    position: absolute;
    bottom: 0;
    right: 5vw;
  }
  @media only screen and (max-width: 800px) {
    .first__palm {
      right: 5vw;
      width: 33%;
    }
  }
  .palm_left {
    left: 5vw;
    -webkit-transform: scaleX(-1);
    transform: scaleX(-1);
  }

  .menu {
    display: none;
    /* display: flex; */
    justify-content: flex-end;
    font-family: "Permanent Marker", sans-serif;
  }
  .menu__text {
    margin-left: 20px;
    color: #ea1059;
    font-size: 1.306em;
    text-decoration: none;
  }

  .intro {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    margin-top: 20vw;
  }
  @media only screen and (max-width: 800px) {
    .intro {
      margin-top: 15vh;
    }
  }
  .intro__container {
    min-width: 330px;
    max-width: 800px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    z-index: 9;
  }
  /* ==== H E L L O ====== */
  .intro__text {
    color: #ea1059;
    position: relative;
    font-family: "Permanent Marker", sans-serif;
    font-size: 6.854em;
    padding: 0;
    margin: 0;
    text-shadow: 3px 3px #371d39;
  }
  .main-text {
    position: relative;
    display: inline-block;
    opacity: 0.7;
  }
  .back-text {
    position: absolute;
    width: 100%;
    left: 0;
    top: 0;
    opacity: 0.3;
    display: inline-block;
  }

  .skew {
    animation: skew 0.95s infinite alternate;
  }

  .glitch {
    animation: glitch 0.8s infinite alternate;
  }

  @keyframes skew {
    0% {
      transform: skew(0deg);
    }
    20% {
      transform: skew(0deg);
      opacity: 1;
    }
    24% {
      transform: skew(-2deg);
      opacity: 0.5;
    }
    25% {
      transform: skew(0deg);
      opacity: 1;
    }
    70% {
      transform: skew(0deg);
    }
    74% {
      transform: skew(2deg);
    }
    76% {
      transform: skew(0deg);
    }
    100% {
      transform: skew(0deg);
    }
  }

  @keyframes glitch {
    0% {
      transform: translate3d(0, 0, 0);
    }
    20% {
      transform: translate3d(0, 0, 0);
    }
    24% {
      transform: translate3d(3px, 4px, 0);
    }
    26% {
      transform: translate3d(0, 0, 0);
    }
    60% {
      transform: translate3d(0, 0, 0);
      opacity: 1;
    }
    64% {
      transform: translate3d(-3px, -2px, 0);
      opacity: 0.3;
    }
    66% {
      transform: translate3d(0, 0, 0);
      opacity: 1;
    }
    70% {
      transform: translate3d(0, 0, 0);
    }
    74% {
      transform: translate3d(1px, -1px, 0);
    }
    76% {
      transform: translate3d(0, 0, 0);
    }
    100% {
      transform: translate3d(0, 0, 0);
    }
  }

  .intro__subtext {
    padding: 20px;
    background-color: rgba(31, 12, 32, 0.8);
    color: #fff;
    max-width: 30vw;
    transition: width 2s;
  }
  @media only screen and (max-width: 800px) {
    .intro__subtext {
      max-width: 60vw;
    }
  }

  .intro__subtext__txt {
    font-size: 1.3em;
    margin: 0;
    text-align: center;
  }
  .section {
    scroll-snap-align: start;
  }
  .imggrp {
    bottom: 0;
    position: relative;
    height: 20vh;
    /* 410px; */
    margin-top: -20vh;
  }
  .sea {
    width: 100%;
    height: 68px;
    position: absolute;
    background-color: #1a0e31;
    z-index: 87;
    bottom: 0;
  }
  .road {
    z-index: 90;
    position: absolute;
    background-color: #1f1337;
    width: 100%;
    height: 20px;
    bottom: 68px;
  }
  .mountains {
    z-index: 89;
    background-repeat: repeat-y;
    background-image: url("../../public/mountains.png");
    position: absolute;
    bottom: 60px;
  }
  .settingsun {
    z-index: 84;
    position: absolute;
    left: 50%;
    margin-left: -17vh;
    top: -20vh;
    width: 30vh;
  }
  .buildings {
    z-index: 91;
    position: absolute;
    left: 10vw;
    bottom: 72px;
    height: auto;
    width: 60vw;
  }

  .animatable {
    /* initially hide animatable objects */
    visibility: hidden;

    /* initially pause animatable objects their animations */
    -webkit-animation-play-state: paused;
    -moz-animation-play-state: paused;
    -ms-animation-play-state: paused;
    -o-animation-play-state: paused;
    animation-play-state: paused;
  }
  .animatablex {
    /* initially hide animatable objects */
    visibility: hidden;

    /* initially pause animatable objects their animations */
    -webkit-animation-play-state: paused;
    -moz-animation-play-state: paused;
    -ms-animation-play-state: paused;
    -o-animation-play-state: paused;
    animation-play-state: paused;
  }

  /* show objects being animated */
  .animated {
    visibility: visible;

    -webkit-animation-fill-mode: both;
    -moz-animation-fill-mode: both;
    -ms-animation-fill-mode: both;
    -o-animation-fill-mode: both;
    animation-fill-mode: both;

    -webkit-animation-duration: 1s;
    -moz-animation-duration: 1s;
    -ms-animation-duration: 1s;
    -o-animation-duration: 1s;
    animation-duration: 1s;

    -webkit-animation-play-state: running;
    -moz-animation-play-state: running;
    -ms-animation-play-state: running;
    -o-animation-play-state: running;
    animation-play-state: running;
  }
  @-webkit-keyframes fadeInDown {
    0% {
      opacity: 0;
      -webkit-transform: translateY(-20px);
    }
    100% {
      opacity: 1;
      -webkit-transform: translateY(0);
    }
  }

  @-moz-keyframes fadeInDown {
    0% {
      opacity: 0;
      -moz-transform: translateY(-20px);
    }

    100% {
      opacity: 1;
      -moz-transform: translateY(0);
    }
  }

  @-o-keyframes fadeInDown {
    0% {
      opacity: 0;
      -o-transform: translateY(-20px);
    }

    100% {
      opacity: 1;
      -o-transform: translateY(0);
    }
  }

  @keyframes fadeInDown {
    0% {
      opacity: 0;
      transform: translateY(-20px);
    }
    100% {
      opacity: 1;
      transform: translateY(0);
    }
  }
  .animated.fadeInDown {
    -webkit-animation-name: fadeInDown;
    -moz-animation-name: fadeInDown;
    -o-animation-name: fadeInDown;
    animation-name: fadeInDown;
  }
</style>

<!-- =========== S T Y L E ========== -->

<!-- =========== H T M L ========== -->

<div class="theapp">

  <div class="bloc first section">
    <div class="menu">
      <a href=".work" class="menu__text">Work</a>
      <a href=".about" class="menu__text">About</a>
      <a href=".contact" class="menu__text">Contact</a>
    </div>

    <div class="sunContainer">
      <img class="sun animatable fadeInDown animation-element" src={sun} alt="setting sun" />
    </div>

    <img class="first__palm animation-element" alt="palm tree" src={palm} />
    <img class="first__palm palm_left" alt="palm tree" src={palm} />

    <div class="intro">
      <div class="intro__container">
        <h3 class="intro__text" data-text="Hello">
          <span class="main-text skew">Hello</span>
          <span class="back-text glitch">Hello</span>
        </h3>
        <!-- transition:fade -->
        <div class="intro__subtext" >
          <h5 class="intro__subtext__txt " >
            I'm a UX/UI designer & front-end developer based in Switzerland.
          </h5>
          <!-- <p class="whisper">(I design app or website and code them)</p> -->
        </div>
      </div>
    </div>

  </div>

  <div class="section">
    <Mid />
    <div class="imggrp">
      <img class="buildings" src="../../buildings.png" alt="buildings" />
      <img
        class="settingsun animatablex fadeInDown"
        src="../../settingsun.png"
        alt="setting sun" />
      <div class="mountains" />
      <div class="road" />
      <div class="sea" />
    </div>
  </div>
  <div class="section">
    <Bottom />
  </div>
</div>
