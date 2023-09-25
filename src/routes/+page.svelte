<script lang="ts">
    import Background from "./Background.svelte";
    let name = "";
    //<!--", BlauFx";-->
    let num = name.length;
    let textToDisplay = name;
    let increment = false;

    const writer = setInterval(changeName, 350);

    function changeName() {
        if (increment == true) {
            if (textToDisplay.length == name.length - 1)
                clearInterval(writer);
            textToDisplay += name[num];
            num++;
        }
        else
        {
            if (textToDisplay.length == 1)
                increment = true;
            textToDisplay = textToDisplay.slice(0, -1);
            num--;
        }
    }
</script>

<svelte:window on:load|once={() => writer}></svelte:window>

<Background />
<!-- <img alt="BlauFx's logo" src="1-sw.png" />-->

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.3/css/all.min.css" integrity="sha512-iBBXm8fW90+nuLcSKlbmrPcLa0OT92xO1BIsZ+ywDWZCvqsWgccV3gFoRBv0z+8dLJgyAHIhR35VZc2oM/gI1w==" crossorigin="anonymous" referrerpolicy="no-referrer" />

<br>
<div class="top-container">
    <div class="child-container">
       <div class="ProfilePicture">
       </div>
       <h1>
          <div id="b-wrapper">
             <div class="jello-horizontal HelloText">Welcome to my page{textToDisplay}!</div>
          </div>
       </h1>
    </div>
    <p id="text">
       Hey there! I'm BlauFx, 19 y/o.<br>
       I try to use my time as efficiently/productively as possible, which sadly doesn't work out quite as often as I would like it to.<br>
       Nevertheless, I strive improve myself and I would like to receive criticism about things that I could improve on.<br>
       <br>
       I'm a full-time Linux enthusiast (I use EndeavourOS).<br>
       In my free time I play video games, develop stuff, watch anime, try to make some AMVs, or tinker around with Linux.<br>
       I am interested in a variety of areas, starting from web development, cybersecurity, games, reverse engineering over to kernel development.<br>
    </p>
    <div class="footer">
       <p2>Social media/contact</p2>
       <a href="https://github.com/BlauFx">
       <i class="fab fa-github fa-2x"></i>
       </a>
       <a href="https://reddit.com/u/BlauFx">
       <i class="fab fa-reddit fa-2x"></i>
       </a>
       <a href="https://osu.ppy.sh/users/9690071">
       <i class="far fa-circle fa-2x"></i>
       </a>
       <a href="https://www.youtube.com/channel/UCEIPf2h0JK-HE6t6y4l_lWQ">
       <i class="fab fa-youtube fa-2x"></i>
       </a>
       <a href="https://twitter.com/OfficialBlauFx">
       <i class="fab fa-twitter fa-2x"></i>
       </a>
       <a href="https://lichess.org/@/BlauFx">
       <i class="fas fa-chess fa-2x"></i>
       </a>
       <a href="mailto:blaufxsup@gmail.com">
       <i class="fas fa-envelope-open fa-2x"></i>
       </a>
       <a href="mailto:contact@blaufx.me">
       <i class="fas fa-envelope-open fa-2x"></i>
       </a>
    </div>
 </div>
 <button class="btn" id="loginBtn" onclick="loginBtn()">Login</button>

 <style>
    body {
    background-color: #323232;
    color: #ebf1ff;
    text-align: center;
    overflow-y: auto;
}

.top-container {
    display: flex;
    flex-direction: column;
    /*position: absolute;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);*/
}

.container {
	display: flex;
	flex-direction: column;
	position: absolute;
	left: 50%;
	top: 50%;
	transform: translate(-50%, -50%);
}

.footer {
    color: #FFFF;
}

.btn {
    position: fixed;
    bottom: 0px;
    right: 0px;
    margin: 10px;

    bottom: 0;
    right: 0;

    background-color: #212121;
    color:  #848484;

    border: 3px solid #848484;
    height: 35px;
    width: 120px;

    -webkit-border-radius: 2px;
    -webkit-border-radius: 3px;

    border: 3px solid #848484;
    border-radius: 3px;

    transition: width 2s, height 2s, transform 2s;
    transform: rotate(0deg);
    transition-delay: ßs;
}

.btn:hover {
    color:  #FFFFFF;

    /*cool animation*/
    height: 70px;
    width: 240px;
    transform: rotate(360deg);
    transition-delay: 0.5s;
}

.btn:focus {
    box-shadow: 0 0 3pt 2pt #a5fbff;
    border-radius: 3px 3px 3px 3px;
    outline: none;
}

.stable {
    background-color: #2a2;
    box-shadow: 0 0 10px #2a2;
}

.testing {
  width: 100%;
  height: 1em;
  display: inline-block;
  animation: bar-blink 2s 1.5s ease-in-out infinite;
}

@keyframes bar-blink {
    30% {
        filter: brightness(70%);
    }
    50% {
        filter: brightness(200%);
        }
    100% {
        filter: brightness(100%);
    }
}

.ProfilePicture {
    background-image: url("/1-sw.webp");
    position: relative;
    flex-wrap: nowrap;
    -webkit-border-radius: 10%;
    -moz-border-radius: 10%;
    -ms-border-radius: 10%;
    -o-border-radius: 10%;
    border-radius: 10%;  
    padding: 7em;
    background-position: 50%;
    background-repeat: no-repeat; 
    margin: center;
    background-size: cover;/*100% 100%;*/
    align-self: center;
}

.ProfilePicture:hover {
    filter:  blur(2px);
}

p {
    font-family: Sans-serif;
    text-align: left;
    margin-left: auto;
    margin-right: auto;
    width: 65em;
    float: left;
    position: relative;
    padding-left: 0%;
    padding-right: 10%;
    left: 7.5%;
}

.text
{
    float: left;
    position: relative;
    left: -50%;
}

p2 {

    display: block; 
    margin-top: 1em; 
    margin-bottom: 1em;

    font-family: Sans-serif;
    text-align: center;
    margin-left: auto;
    margin-right: auto;
    width: 55%;
}

a {
    height: 100%;
    padding: 20px;
    /* font-size: -webkit-xxx-large */;

    text-decoration: none;
    color: #FFF;
}

.child-container {
    flex-wrap: wrap;
    flex-direction:  column;
    align-content: center;
    justify-content: center;
    display: flex;
    margin-top: 5%;
}

b {
	color : #FFF;
	margin: auto;
	transition: 3s;
}

#b-wrapper {
    display: flex;

    margin: auto;
    transition: 5s;

    -webkit-animation: fadeInOut 10s;
    animation-iteration-count: 1;   
}

.HelloText:hover {
	animation-duration: 10s;
	animation-name: rainbow;
	animation-iteration-count: infinite;
	letter-spacing: 0.2em;
	transition: 1.5s;
	text-align: center;
	text-indent: 0.2em;
}


.jello-horizontal {
	/*-webkit-animation: jello-horizontal 0.9s both;*/
	        animation: jello-horizontal 0.9s both;
            animation-iteration-count: 1;
            transition: 1s;
}

@keyframes fadeInOut {
	0% {
        opacity: 0;
    }

    40% {
       opacity: 1;
    }

    80% {
       opacity: 1;
    }
    100% {
       opacity: 0;
    }
}

@keyframes rainbow {
		100%,0%{
			color: rgb(255,0,0);
		}
		8%{
			color: rgb(255,127,0);
		}
		16%{
			color: rgb(255,255,0);
		}
		25%{
			color: rgb(127,255,0);
		}
		33%{
			color: rgb(0,255,0);
		}
		41%{
			color: rgb(0,255,127);
		}
		50%{
			color: rgb(0,255,255);
		}
		58%{
			color: rgb(0,127,255);
		}
		66%{
			color: rgb(0,0,255);
		}
		75%{
			color: rgb(127,0,255);
		}
		83%{
			color: rgb(255,0,255);
		}
		91%{
			color: rgb(255,0,127);
		}
}

/* ----------------------------------------------
 * Generated by Animista on 2021-5-29 17:51:34
 * Licensed under FreeBSD License.
 * See http://animista.net/license for more info. 
 * w: http://animista.net, t: @cssanimista
 * ---------------------------------------------- */

/**
 * ----------------------------------------
 * animation jello-horizontal
 * ----------------------------------------
 */
@-webkit-keyframes jello-horizontal {
  0% {
    -webkit-transform: scale3d(1, 1, 1);
            transform: scale3d(1, 1, 1);
  }
  30% {
    -webkit-transform: scale3d(1.25, 0.75, 1);
            transform: scale3d(1.25, 0.75, 1);
  }
  40% {
    -webkit-transform: scale3d(0.75, 1.25, 1);
            transform: scale3d(0.75, 1.25, 1);
  }
  50% {
    -webkit-transform: scale3d(1.15, 0.85, 1);
            transform: scale3d(1.15, 0.85, 1);
  }
  65% {
    -webkit-transform: scale3d(0.95, 1.05, 1);
            transform: scale3d(0.95, 1.05, 1);
  }
  75% {
    -webkit-transform: scale3d(1.05, 0.95, 1);
            transform: scale3d(1.05, 0.95, 1);
  }
  100% {
    -webkit-transform: scale3d(1, 1, 1);
            transform: scale3d(1, 1, 1);
  }
}
@keyframes jello-horizontal {
  0% {
    -webkit-transform: scale3d(1, 1, 1);
            transform: scale3d(1, 1, 1);
  }
  30% {
    -webkit-transform: scale3d(1.25, 0.75, 1);
            transform: scale3d(1.25, 0.75, 1);
  }
  40% {
    -webkit-transform: scale3d(0.75, 1.25, 1);
            transform: scale3d(0.75, 1.25, 1);
  }
  50% {
    -webkit-transform: scale3d(1.15, 0.85, 1);
            transform: scale3d(1.15, 0.85, 1);
  }
  65% {
    -webkit-transform: scale3d(0.95, 1.05, 1);
            transform: scale3d(0.95, 1.05, 1);
  }
  75% {
    -webkit-transform: scale3d(1.05, 0.95, 1);
            transform: scale3d(1.05, 0.95, 1);
  }
  99% {
    -webkit-transform: scale3d(1, 1, 1);
            transform: scale3d(1, 1, 1);
  }
}

 </style>