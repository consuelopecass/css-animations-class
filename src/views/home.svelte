<div class="container" >
    <div class="box hover-transition"></div>
    <div class="box rotated"></div>
    <div class="box colored"></div>
    <div class="box multiple-transitions"></div>
    <div class="box multiple-animation"></div>
    <div class="box orchestated-transition"></div>
</div>

<style>
    @keyframes rotateBox {
        100% {
            transform: rotateZ(360deg);
        }
    }

    @keyframes rotateColor {
        0% {
            background-color: hsl(0 100% 50%);
        }
        20% {
            background-color: hsl(72deg 100% 50%);
        }
        40% {
            background-color: hsl(144deg 100% 50%);
        }
        60% {
            background-color: hsl(216eg 100% 50%);
        }
        80% {
            background-color: hsl(288deg 100% 50%);
        }
        100% {
            background-color: hsl(360deg 100% 50%);
        }
    }

    .container {
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
    }

    .rotated {
        animation-name: rotateBox;
        animation-duration: 1000ms;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
    }

    .colored {
        animation-name: rotateColor;
        animation-duration: 10000ms;
        animation-timing-function: linear;
        animation-iteration-count: infinite;
    }

    .box {
        display: block;
        width: 100px;
        height: 100px;
        background: teal;
        transition: all 1000ms linear;
    }

    .hover-transition:hover {
        transform: rotateZ(360deg) scale(0.7);
    }

    .multiple-transitions {
        transition: opacity 4000ms ease, transform 250ms linear;
        transform: scale(1);
        opacity: 1;
    }

    .multiple-transitions:hover {
        transform: scale(1.3);
        opacity: 0.1;
    }

    .multiple-animation {
        animation-name: rotateBox, rotateColor;
        animation-duration: 1500ms, 2500ms;
        animation-timing-function: ease, linear;
        animation-iteration-count: infinite;
    }

    .orchestated-transition {
        transition: background-color 250ms linear 500ms,
                    transform 250ms ease 0ms;
        transform: scale(1);
    }

    .orchestated-transition:hover {
        background-color: orange;
        transform: scale(1.5);
        transition: background-color 250ms linear 0ms,
                    transform 250ms ease 500ms;
    }
</style>
