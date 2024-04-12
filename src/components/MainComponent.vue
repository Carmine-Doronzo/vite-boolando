<script>
    import CardComponent from './CardComponent.vue'
    import {productsArray} from '../store.js'
    import axios from 'axios'

    export default{
        data(){
            return{
                product:productsArray.db,
                lenght:0
            }
        },
        components:{
            CardComponent,
            
        },
        methods:{
         
        },
        mounted(){
            
            axios.get('http://localhost:3000/products').then((response)=>{
                
                for(let i = 0;i <response.data.length; i++ ){
                    const result = response.data[i]
                    this.product.push(result)

                    this.lenght++
                
                }

                
                
                //const result = response.data
                //this.product = result
                //console.log(result)

            })

            

        }, 
    }
    
    

</script>

<template>
    <main>
        
        <section>
            
            <div class="container">
                
                
                    <ul v-if="this.product.length === lenght" class="row-main">
                        <li class="col-main" v-for="(item,i) in product" :key="item.id">
                            <CardComponent  :item="item" />
                        </li>
                    </ul>
                    <!-- <div>{{ this.lenght }}</div> -->
                    
                    <!-- <div v-for="(item,i) in product" :key="i" class="col-main" >
                        
                        <img class="main-image" :src="`/img/${item.frontImage}`" alt="">
                        <img class="second-image" src="/img/1b.webp" alt="">
                        
                        <div class="line-height">
                            
                            <h6>Levi's</h6>
                            <h4>RELAXED FIT TEE UNISEX</h4>
                            <h5 class="font-red display">14,99 &euro;</h5> <span class="line-through">29,99 &euro;</span>
                            
                        </div>
                        
                        <div class="position">
                            <span class="badge bg-red">-50%</span>
                            <span class="badge bg-green left">Sostenibilita'</span>
                        </div>
                        
                        <button class="heart bg-white">&hearts;</button>
                    
                    </div> -->
                    
                    <!-- <div class="col-main">
                        
                        <img class="main-image" src="/img/2.webp" alt="">
                        <img class="second-image" src="/img/2b.webp" alt="">
                        
                        <div class="line-height">
                            
                            <h6>Levi's</h6>
                            <h4>RELAXED FIT TEE UNISEX</h4>
                            <h5 class="font-red display">14,99 &euro;</h5> <span class="line-through">29,99 &euro;</span>
                            
                        </div>
                        
                        <div class="position">
                            
                            <span class="badge bg-red">-50%</span>
                        
                        </div>
                        
                        <button class="heart bg-white">&hearts;</button>
                        
                        
                    </div>
                    
                    <div class="col-main">
                        
                        <img class="main-image" src="/img/3.webp" alt="">
                        <img class="second-image" src="/img/3b.webp" alt="">
                        
                        <div class="line-height">
                            
                            <h6>Levi's</h6>
                            <h4>RELAXED FIT TEE UNISEX</h4>
                            <h5 class="font-red display">14,99 &euro;</h5> <span class="line-through">29,99 &euro;</span>
                            
                        </div>
                        
                        <div class="position">
                            
                            <span class="badge bg-red">-50%</span>
                        
                        </div>
                        
                        <button class="heart bg-white">&hearts;</button>
                    
                    </div>
                    
                    <div class="col-main">
                        
                        <img class="main-image" src="/img/4.webp" alt="">
                        <img class="second-image" src="/img/4b.webp" alt="">
                        
                        <div class="line-height">
                            
                            <h6>Levi's</h6>
                            <h4>RELAXED FIT TEE UNISEX</h4>
                            <h5 class="font-red display">14,99 &euro;</h5> <span class="line-through">29,99 &euro;</span>
                            
                        </div>
                            
                            <div class="position">
                                
                                <span class="badge bg-red">-50%</span>
                                <span class="badge bg-green left">Sostenibilita'</span>
                            
                            </div>
                        
                        <button class="heart bg-white">&hearts;</button>
                            
                    </div>
                    
                    <div class="col-main">
                        
                        <img class="main-image" src="/img/5.webp" alt="">
                        <img class="second-image" src="/img/5b.webp" alt="">
                       
                        <div class="line-height">
                            
                            <h6>Levi's</h6>
                            <h4>RELAXED FIT TEE UNISEX</h4>
                            <h5 class="font-red display">14,99 &euro;</h5> <span class="line-through">29,99 &euro;</span>
                            
                        </div>

                        
                        <button class="heart bg-white">&hearts;</button>
                        
                    </div>
                    
                    <div class="col-main">
                        
                        <img class="main-image" src="/img/6.webp" alt="">
                        <img class="second-image" src="/img/6b.webp" alt="">
                        
                        <div class="line-height">
                            
                            <h6>Levi's</h6>
                            <h4>RELAXED FIT TEE UNISEX</h4>
                            <h5 class="font-red display">14,99 &euro;</h5> <span class="line-through">29,99 &euro;</span>
                            
                        </div>
                        
                        <div class="position">
                            
                            <span class="badge bg-green">Sostenibilita'</span>
                            
                        
                        </div>

                        <button class="heart bg-white">&hearts;</button>
                    
                    </div> -->
                
                

            </div>
        
        </section>
    
    </main>
</template>

<style lang="scss" scoped>
    @use'../style/partials/bg-color';
    @use'../style/partials/layouts';
    @use'../style/partials/reset';
    @use'../style/partials/style';
    @use'../style/partials/utility';
</style>
