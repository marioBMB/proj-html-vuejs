<template>
  
    <footer class='section-more'>

        <div class="container">

            <div class="row">
                
                <div class="col">
                </div>
                <div class="col">
                    <a href="link_url">{{link_text}}</a>
                </div>
                <div class="col">
                </div>
            </div>
        </div>
    </footer>

</template>

<script>

    
    export default {
        name: "SectionFooterMore",
        props: {
            link_text: String,
            link_url: String,
        }
    }
</script>

<style lang='scss'>

    .section-more {

        margin: 75px auto;
        
        text-transform: uppercase;
        font-weight: 200;
        text-align: center;

        .row {
            height: 1.8rem;
            padding: 0 20px;
            align-items: center;
        }
        

        .col:first-of-type {
            height: 100%;
            border-top: 3px solid #eee;
            margin-right: 50px;
        }

        a {
            text-decoration: none;
            color: #555;
            font-size: 1rem;
            display: block;
            
        }

        .col:last-of-type {
            line-height: 1.8rem;
            border-bottom: 3px solid #eee;
            margin-left: 50px;

        }
    }

    #main-middle {
        .section-more {

            .col:first-of-type, .col:last-of-type {
                border-color: white;
            }
        }
    }


</style>