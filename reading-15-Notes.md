# **Reading Assignment 15 - CSS Transforms, Transitions, and Animations**

1. ## Transforms
  + ### CSS Transform Property
    + Just like OOP engines like Unity, CSS also contains a Transform property which governs movement and transformations of individual elements.
      + Transform Properties:
      .scale {
  transform: scale(1.5);
}
      .rotate {
  transform: rotate(-55deg);
}
      .skew {
  transform: skew(5deg, -20deg);
}
      .translate {
  transform: translate(-10px, 25%);
}

  + ### Transitions
    + CSS provides a number of animated transitions to increase appeal of html elements:
      + Fade in
      + .fade
        {
                opacity:0.5;
        }
        .fade:hover
        {
                opacity:1;
        }      
      + Change color
        .color:hover
        {
                background:#53a7ea;
        }
      + Grow & Shrink
        .grow:hover
        {
                -webkit-transform: scale(1.3);
                -ms-transform: scale(1.3);
                transform: scale(1.3);
        }
        .shrink:hover
        {
                -webkit-transform: scale(0.8);
                -ms-transform: scale(0.8);
                transform: scale(0.8);
        }
      + Rotate elements
        .rotate:hover
        {
                -webkit-transform: rotateZ(-30deg);
                -ms-transform: rotateZ(-30deg);
                transform: rotateZ(-30deg);
        }
      + Square to circle
        .circle:hover
        {
                border-radius:50%;
        }
      + 3D shadow
        .threed:hover
        {
                box-shadow:
                        1px 1px #53a7ea,
                        2px 2px #53a7ea,
                        3px 3px #53a7ea;
                -webkit-transform: translateX(-3px);
                transform: translateX(-3px);
        }
      + Swing
        @-webkit-keyframes swing
        {
            15%
            {
                -webkit-transform: translateX(5px);
                transform: translateX(5px);
            }
            30%
            {
                -webkit-transform: translateX(-5px);
               transform: translateX(-5px);
            } 
            50%
            {
                -webkit-transform: translateX(3px);
                transform: translateX(3px);
            }
            65%
            {
                -webkit-transform: translateX(-3px);
                transform: translateX(-3px);
            }
            80%
            {
                -webkit-transform: translateX(2px);
                transform: translateX(2px);
            }
            100%
            {
                -webkit-transform: translateX(0);
                transform: translateX(0);
            }
        }
        @keyframes swing
        {
            15%
            {
                -webkit-transform: translateX(5px);
                transform: translateX(5px);
            }
            30%
            {
                -webkit-transform: translateX(-5px);
                transform: translateX(-5px);
            }
            50%
            {
                -webkit-transform: translateX(3px);
                transform: translateX(3px);
            }
            65%
            {
                -webkit-transform: translateX(-3px);
                transform: translateX(-3px);
            }
            80%
            {
                -webkit-transform: translateX(2px);
                transform: translateX(2px);
            }
            100%
            {
                -webkit-transform: translateX(0);
                transform: translateX(0);
            }
        }        
        Note: This animation simply moves the element left and right, now all we need to do is apply it:
        .swing:hover
        {
                -webkit-animation: swing 1s ease;
                animation: swing 1s ease;
                -webkit-animation-iteration-count: 1;
                animation-iteration-count: 1;
        }
      + Inset border
        .border:hover
        {
                box-shadow: inset 0 0 0 25px #53a7ea;
        }
        
1. ## Examples Using Transitions
  + ### Animated 404:
  **HTML:**
  `<h1>4</h1>`
  `<h1>0</h1>`
  `<h1>4</h1>`
  **CSS:**
  body {
  margin:0;
  font-family:sans-serif;
  color:#f25252;
  background:#f7f7f7;
  }
  h1 {
    font-size:11rem;
    position:absolute;
    transform:translate(-50%,-50%);
    margin:0;
  }
  h1:nth-of-type(1){
    animation: range 4s infinite;
  }
  h1:nth-of-type(2){
    left:50%;
    top:50%;
    animation: size 4s infinite;
  }
  h1:nth-of-type(3){
    animation: range2 4s infinite;
  }
  @keyframes range {
    0%  {left:42%;top:50%;font-size:11rem;}
    25% {left:50%;top:40%;font-size:4.5rem;}
    50% {left:58%;top:50%;font-size:11rem;}
    75% {left:50%;top:60%;font-size:4.5rem;}
    100%{left:42%;top:50%;font-size:11rem;}
  }
  @keyframes range2 {
    0%  {left:58%;top:50%;font-size:11rem;}
    25% {left:50%;top:60%;font-size:4.5rem;}
    50% {left:42%;top:50%;font-size:11rem;}
    75% {left:50%;top:40%;font-size:4.5rem;}
    100%{left:58%;top:50%;font-size:11rem;}
  }
  @keyframes size {
    0%  {font-size:11rem;}
    25% {font-size:26rem;}
    50% {font-size:11rem;}
    75% {font-size:26rem;}
    100%{font-size:11rem;}
  }
  
 + ### Bouncing Ball Transforms to Square:
 **HTML:**
 `<div class="animation animation-1">`
  `<div class="ball"></div>`
  `</div>`
  `<div class="animation animation-2">`
  `<div class="ball"></div>`
  `</div>`
  `<div class="animation animation-3">`
  `<div class="ball"></div>`
  `</div>`	
 **CSS:**
 /* Animation -------------------- */

@keyframes balltransform {
	0% {
		border-radius:50%;
		height:100%;
		width:60%;
	}
	29% {
		height:100%;
		width:60%;
	}
	30% {
		height:50%;
		width:100%;
	}
	40% {
		height:80%;
		width:80%;
	}
	59% {
		height:100%;
		width:60%;
	}
	60% {
		height:50%;
		width:100%;
		border-radius:50%;
		transform:rotate(0);
	}
	100% {
		height:80%;
		width:80%;
		border-radius:0;
		transform: rotate(-180deg);
	}
}

@keyframes ballbounce {
	/* up */
	0% {
		top:-30%;
		animation-timing-function: ease-in;
	}
	/* floor */
	30% {
		top:80%;
		animation-timing-function: ease-out;
	}
	/* up */
	40% {
		top: 20%;
	}
	/* up */
	45% {
		top:17%;
		animation-timing-function: ease-in;
	}
	/* floor */
	60% {
		top:80%;
		animation-timing-function: ease-out;
	}
	/* up */
	75% {
		top:30%;
	}
	90% {
		top:25%;
		animation-timing-function: ease-in;
	}
	/* floor */
	100% {
		top:110%;
		animation-timing-function:ease-out;
	}
}

@keyframes scalemask {
	0% {
		mask-size:0%;
	}
	65% {
		mask-size:0%;
	}
	78%,100% {
		mask-size:300%;
	}
}

@keyframes scalemask2 {
	0% {
		-webkit-mask-size:0%;
	}
	83% {
		-webkit-mask-size:0%;
	}
	100% {
		-webkit-mask-size: 300%;
	}
}

* {
	box-sizing:border-box;
}

body {
	padding:0;
	margin: 0;
}

/* Ball -------------------- */
.ball {
	width:5rem;
	height:5rem;
	left:50%;
	position:absolute;
	z-index:1;
	margin-left:-2.5rem;
	animation:ballbounce 4s 1s infinite;
	animation-fill-mode:both;
}

.ball:after {
	content:" ";
	color:#fff;
	display:block;
	margin:auto;
	border-radius:50%;
	background:#fff;
	width:100%;
	height:100%;
	animation: balltransform 4s 1s infinite;
}

/* Animation containers -------------------- */
.animation {
	background:#297acb;
	height:100vh;
	width:100vw;
	position:relative;
	z-index:1;
}

.animation-2,
.animation-3 {
	position:absolute;
	top:0;
	left:0;
	-webkit-mask-size:0;
	-webkit-mask-image:radial-gradient(circle closest-side,black 0%,black 90%,rgba(255,255,255,0) 92%);
	-webkit-mask-repeat:no-repeat;
	-webkit-mask-position:center center;
	animation-fill-mode:both;
}

.animation-2 {
	background:purple;
	animation:scalemask 4s 1s infinite;
}

.animation-3 {
	animation:scalemask2 4s 1s infinite;
}

.animation-2 .ball:after {
	background: #297acb;
}
