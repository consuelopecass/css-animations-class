<div class="container" >

    <div class="caja hover"></div>
    <div class="caja animacion"></div>
    <div class="caja color"></div>
    <div class="caja multi-animacion"></div>
    <div class="caja orquestacion"></div>
   
 

</div>

<style>

    @keyframes RotarCaja {
        0%{
            transform: rotateZ(0);
        }
        50%{
            transform: rotateZ(180deg);
        }
        100%{
            transform: rotateZ(360deg);
        }
    }

    @keyframes RotarColor {
        0%{
            background-color: hsl(0deg, 100%, 50%);
        }

        20%{
            background-color: hsl(72deg, 100%, 50%);
        }
        40%{
            background-color: hsl(144deg, 100%, 50%);
        }
        60%{
            background-color: hsl(216deg, 100%, 50%);
        }
        80%{
            background-color: hsl(288deg, 100%, 50%);
        }
        100%{
            background-color: hsl(360deg, 100%, 50%);
        }

        
    }

    .container {
        display: flex;
        gap: 10px;
        flex-wrap: wrap;
    }

    .caja {
        width: 100px;
        height: 100px;
        background: teal;
        transition: all 500ms linear;
        transition: opacity 1500ms linear, transform 2500ms ease;
    }

    .caja:hover {
        opacity: 0;
        transform: rotateZ(360deg);
    }

    .animacion {
        animation-name: RotarCaja;
        animation-duration: 1500ms;
        animation-timing-function: linear;
        animation-iteration-count: infinite;

        
    }

    .color {

        animation-name: RotarColor;
        animation-duration: 1500ms;
        animation-timing-function: linear;
        animation-iteration-count: infinite;

    }

    .multi-animacion {

        animation-name: RotarCaja, RotarColor;
        animation-duration: 5s 1000ms;
        animation-timing-function: ease, linear;
        animation-iteration-count: infinite;
        
    }

    .orquestacion {
        transition: background-color 500ms linear, transform 1s ease 500ms; 
    }

    .orquestacion:hover {
        background-color: orange;
        transform: scale(1.5);
    }


</style>
