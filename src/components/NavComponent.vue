<script>
    export default{
        data(){
            return{
                links:{
                    donna:'Donna',
                    uomo:'Uomo',
                    bimbo:'Bambini'
                },
                hearts:{
                    heart0:'♥︎',
                    heart1:'♥︎',
                    heart2:'♥︎',
                }
            }
        }
    }
</script>

<template>
    <header>
        <nav>
            
                
                <div class="row-nav bg-orange font-white">

                    <div class="col-nav  ">
                        <a v-for="(link,i) in links" href="#">{{ link }}</a>
                        <!-- <a href="#">Uomo</a>
                        <a href="#">Bambini</a> -->
                    </div>
                    
                    <div class="col-nav">
                        <img class="nav-logo" src="/img/boolean-logo.png" alt="">

                    </div>
                    
                    <div class="col-nav ">
                        <a v-for="(heart,i) in hearts" href="#">{{ heart }}</a>
                        
                        

                    </div>

                </div>
            
            
        
        </nav>
    </header>
</template>

<style lang="scss" scoped>
    
   @use'../style/partials/bg-color';
    @use'../style/partials/layouts';
    @use'../style/partials/reset';
    @use'../style/partials/style';
    @use'../style/partials/utility';
    

</style>