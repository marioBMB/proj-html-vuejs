<template>
  
  <main>


    <div id="main-top">

        <Jumbotron :jumbo_img="require('../../assets/img/home-slider-62528242.jpg')"
                    title="Building inspiring spaces" subtitle="We Build Inspiring Residential &amp; commercial Spaces"/>

        <section class="cta">
            <h2 class='cta-title'>Do you have a construction project we can help with?</h2>
            <a href="#" class="btn cta reverse-bg">get a free quote</a>
        </section>

        <section id='services'>

            <div class="container">


                <SectionHeader title="Specialist in modern construction" 
                            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus, tempore sint dicta saepe aspernatur placeat tenetur quisquam hic labore ullam voluptates!
                            Nemo eius nihil sit fugit.Error, provident. Porro, debitis!"/>
        
            
                <div class="body row">

                    <div v-for="(item, index) in services_data" :key="index" class="info-box col">
                        <div class="icon-box">
                            <i :class="item.icon"></i>
                        </div>
                        <h2>{{item.name}}</h2>
                        <p>{{item.desc}}</p>
                    </div>

                </div>
            </div>
        </section>

        <section id="stats" class='insert'>
            
            <div class="container">

                <div class="row">

                    <div v-for="(item, index) in stats_data" :key="index" class="col info-wrapper">

                        <i :class='item.icon'></i>
                        <h2>{{item.amount}}</h2>
                        <h4>{{item.name}}</h4>
                    </div>
                </div>
            </div>

        </section>

        <section id="our-works">

           <div class="container">

                <SectionHeader title="Explore Recent Work" 
                               subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus, tempore sint dicta saepe aspernatur placeat tenetur quisquam hic labore ullam voluptates!
                               Nemo eius nihil sit fugit.Error, provident. Porro, debitis!"/>
            
                <div class="body row img-gallery">

                    <div class="col">
                        <img :src="require('../../assets/img/project1-featured-294276386-400x400.jpg')" alt="">
                    </div>
                    <div class="col">
                        <img :src="require('../../assets/img/project2-featured-15013609-400x400.jpg')" alt="">
                    </div>
                    <div class="col">
                        <img :src="require('../../assets/img/project3-featured-189023420-400x400.jpg')" alt="">
                    </div>
                </div>
                
                <SectionFooterMore link_text="View all projects" link_url="#"/>
                    
            </div>
        </section>
    </div>


    <div id="main-middle">

        <section id='our_values'>

            <div class="container">

                <SectionHeader title="Our core values" 
                            subtitle="Lorem ipsum dolor sit amet consectetur adipisicing elit. Voluptatibus, tempore sint dicta saepe aspernatur placeat tenetur quisquam hic labore ullam voluptates!
                            Nemo eius nihil sit fugit.Error, provident. Porro, debitis!"/>


                <div class="row">

                    <div v-for="(item, index) in values_data" :key="index" class="col j-center icon-bg">
                        <div class="icon-box border-0" :style="'background-color: '+item.icon_bg">
                            <i :class="item.icon" ></i>
                        </div>
                        <h3>{{item.name}}</h3>
                        <p>{{item.desc}}</p>
                    </div>

                </div>
                    
            </div>

        </section>

        <section id="testimonials" class='insert'>

            <div class="container">
                
                    <SectionHeader title="Our home owners says" subtitle="" />
                
                <div class="carousel t-center">

                    <div class="content">

                        <img class='avatar' :src="require('../../assets/img/'+reviews_data[activeIndex].avatar)" alt="">
                        <h4 class='review-text'>"{{reviews_data[activeIndex].text}}"</h4>
                        <h4 class='author-info'>{{reviews_data[activeIndex].name}} * {{reviews_data[activeIndex].role}}</h4>
                    </div>

                    <div class="circles-container">
                        <div v-for="(item, index) in reviews_data.length" :key="'circle'+index" class='circle' :class="{'active': index == activeIndex}" @click="setActiveImg(index)"></div>
                    </div>
                </div>

            </div>
        </section>

        <section id="news">

            <SectionHeader title="Latest News" subtitle="Lorem ipsum dolor sit, amet consectetur adipisicing elit. Laboriosam nobis suscipit libero, minima repudiandae consequatur aspernatur consectetur saepe consequuntur iusto assumenda officia dolore. Placeat, accusantium. Eum vel rem modi ex!" />

            <div class="row">


                <div class="col">
                    <img src="" alt="">
                    <h3 class='post-title'></h3>
                    <div class="post-date"></div>
                    <p class="post-text"></p>
                </div>
            </div>

        </section>
    </div>

    <div id="main-bottom">
        
    </div>

  </main>
</template>

<script>

    import Jumbotron from "../sections/Jumbotron.vue";
    import SectionHeader from "../commons/SectionHeader.vue";
    import SectionFooterMore from "../commons/SectionFooterMore.vue";


    import services_dataJSON from "../../data/services.json";
    import stats_dataJSON from "../../data/stats.json";
    import values_dataJSON from "../../data/values.json";
    import reviews_dataJSON from "../../data/reviews.json";


    export default {
        name: "Main",
        components: {
            Jumbotron,
            SectionHeader,
            SectionFooterMore
        },
        data() {

            return {

                activeIndex: 0,
                services_data: services_dataJSON,
                stats_data: stats_dataJSON,
                values_data: values_dataJSON,
                reviews_data: reviews_dataJSON,

            }
        },
        methods: {
            setActiveImg(index){
                this.activeIndex = index;
            }
        },
        created(){
            console.log(this.services_data);
        }
    }

</script>

<style lang='scss'>


    #main-middle {
        background-color: #f5f5f5;
        padding: 10px 0;
    }

    #main-top {
        background-color: white;
    }
    
    section.cta {
        background-color: #fed03d;
        height: 150px;
        line-height: 150px;
        color: #333;
        position: relative;
        margin: 0 0 50px 0;
        

        .cta-title {
            font-size: 2.2rem;
            font-weight: 300;
            text-transform: capitalize;
            text-align: center;
        }

        .btn.cta {
            position: absolute;
            left: 50%;
            bottom: 0;
            transform: translate(-50%, 50%);
            border: 1px solid white;
            line-height: normal;
            font-variant: small-caps;
            font-size: 0.9rem;
            padding: 15px 30px;

            &:hover {
                background-color: white !important;
                border-color: black;
                color: black !important;
            }
        }
    }



    section#stats {
        background-image: url(../../assets/img/home-244125289.jpg);
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
        height: 600px;
        display: flex;
        align-items: center;

        .container {
            width: 80%;
        }
    }

    section#stats .info-wrapper {
        color: #fed03d;
        text-transform: uppercase;
    } 


    section#testimonials {
        background-image: url(../../assets/img/home-parallax-144609983.jpg);
        background-size: cover;
        background-repeat: no-repeat;
        background-position: 0% 20%;
        // background-position: 0% -120%;
        min-height: 700px;
        background-attachment: fixed;

        .container {
            width: 50%;
        }

        .review-text {
            font-style: italic;
            line-height: 1.5;
            font-weight: 400;
        }

        .author-info {
            text-transform: uppercase;
            font-weight: 700;
        }
    }

    .insert {
        position: relative;
        margin: 0;
        top: -50px;
        background-color: inherit;

        .container {
            width: 50%;
        }

        .section-heading {
            margin-bottom: 0;
            padding-bottom: 0;

            h1 {
                margin-bottom: 0;
                font-size: 2rem;
            }
        }
    }

    .insert::before {
        content: "";
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        background-color: inherit;
        top: -50px;
        width: 130vw;
        height: 150px;
        border-radius: 50% / 100%;
        border-top-left-radius: 0;
        border-top-right-radius: 0;
    }

    .insert + section {
        position: relative;
        margin-top: 0;
    }

    .insert + section::before {
        content: "";
        position: absolute;
        left: 50%;
        top: -200px;
        transform: translateX(-50%);
        background-color: inherit;
        width: 130vw;
        height: 150px;
        border-radius: 50% / 100%;
        border-bottom-left-radius: 0;
        border-bottom-right-radius: 0;
    }
    

    .insert .container {
        padding-top: 75px;
        color: white;
        width: 80%;
        padding-bottom: 100px;
    }

    .info-wrapper {
        
        text-align: center;
        height: 170px;
        display: flex;
        justify-content: space-evenly !important;
        margin: 0;

        h4 {
            color: white;
            flex-wrap: nowrap;
            font-weight: 400;
            font-size: 0.9rem;
        }

        .svg-inline--fa{
            font-size: 4rem;
        }

        h2 {
            font-weight: 400;
            font-size: 3.5rem;
            font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif

        }
    }

    .img-gallery {

        .col {
            flex: 0 0 auto;
            margin: 0 20px;
        }
    }


    .icon-box {
        color: #777;
        border: 1px solid black; 
        border-radius: 50%;
        min-width: 40px;
        min-height: 40px;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        box-sizing: content-box;
        padding: 10%;
    }

    .icon-bg .icon-box {
        border: none;
        color: white;
    }

    .avatar {
        border: none;
        border-radius: 50%;
        min-width: 50px;
        min-height: 50px;
        display: inline-flex;
    }


    .info-box {
        background-color: #f5f5f5;
        width: 200px;
        text-align: center;
        padding: 20px 30px;
        margin: 15px;
        border-radius: 7px;

        h2 {
            font-weight: 300;
            font-size: 2rem;
            margin: 0.7rem;
            color: #444;
        }
    }


    .circle {

        width: 15px;
        height: 15px;
        margin: 20px 5px;
        display: inline-block;
        border: 1px solid white;
        border-radius: 50%;
        cursor: pointer;
    }

    .circle.active {
        background-color: white;
    }


    .carousel {

        .content {
        }
        .content > *{            
            margin-bottom: 20px;
        }
        
        .circles-container {
            position: absolute;
            bottom: 120px;
            left: 50%;
            transform: translateX(-50%);
        }
    }


</style>