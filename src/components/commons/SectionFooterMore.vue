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
            border-top: 2px solid #eee;
        }

        a {
            text-decoration: none;
            color: #555;
            font-size: 0.9rem;
            display: block;
            
        }

        .col:last-of-type {
            line-height: 1.8rem;
            border-bottom: 2px solid #eee;
        }
    }
</style>