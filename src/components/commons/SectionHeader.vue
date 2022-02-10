<template>
    
    <header class="section-heading">
        <h1 class="heading">{{title}}</h1>
        <p>{{subtitle}}</p>
    </header>

</template>

<script>

    export default {
        name: "SectionHeader",
        props: {
            title: String,
            subtitle: String,
        }

    }
</script>

<style lang="scss">

    .section-heading {
        
        width: 70%;
        text-align: center;
        margin: 50px auto;


        .heading {
            margin: 20px;
            font-size: 2.2rem;
            font-weight: 200;
            text-transform: capitalize;

            &::after {
                content:"";
                display:block;
                
                border-bottom: 2px solid #fed03d;
                width: 200px;
                margin: 25px auto;
                margin-bottom: 40px;
            }
        }

         p {
                font-weight: 300;
                line-height: 1.9;
                color: #777;
                font-size: 1rem;
        }
    }

</style>