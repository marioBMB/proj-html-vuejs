<template>
  
    <div class="jumbotron" :style="'background-image: url('+jumbo_img+');'">

        <div class="container">

            <h1 class="title">{{title}}</h1>
            <h3 class="subtitle">{{subtitle}}</h3>
            <a class='btn reverse-bg left' href="#">Explore recent work</a>
            <a class='btn right' href="#">Get a quote today</a>
        </div>

        <div class="icon-box">
            <div class='text offer'><sup>$</sup>39</div>
            <p>On Sale</p>
        </div>
    </div>

</template>

<script>
    export default {

        name: "Jumbotron",

        props: {
            jumbo_img: String,
            title: String,
            subtitle: String
        }
    }
</script>

<style lang='scss'>


    .jumbotron {
        background-repeat: no-repeat;
        background-size: cover;
        background-position: center;
        height: 600px;
        width: 100%;
        background-color: #3e3e3e;
        color: white;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
        align-content: center;
        position: relative;
       

        .container {

            width: max-content;
            padding: 20px;
            text-align: center;
            height: 40%;
            display: flex;
            flex-direction: row;
            justify-content: center;
            flex-wrap: wrap;


            .left, .right {
                margin: 20px 5px;
                width: 20%;
            }

            .title {
                text-transform: uppercase;
                width: 100%;
                font-size: 2.9rem;
                font-weight: 600;
            }

            .subtitle {

                font-size: 1.3rem;
                width: 100%;
                color: #f7ca3a;
                font-weight: 300;
            }

            .btn {
                min-width: 250px;
            }
        }

        .icon-box {
            position: absolute;
            right: 10px;
            top: 10px;
            background-color: rgba(255,255,255, 0.7);
            color: black;
            border-radius: 5px;
            padding: 10px;

            .offer {
                color: green;
            }

            .text {
                font-size: 2rem;
            }

            sup, p {
                font-size: 1rem;
            }
        }


    }
</style>