<script>
import NavComponent from './components/NavComponent.vue'
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'
import {productsArray} from './store.js'
import axios from 'axios'
 
export default{
    components:{
    NavComponent,
    MainComponent,
    FooterComponent
    },
    data(){
      return{
      product:productsArray.db
      }
    },
    mounted(){
            
            axios.get('http://localhost:3000/products').then((response)=>{
                
                for(let i = 0;i <response.data.length; i++ ){
                    const result = response.data[i]
                    productsArray.db.push(result)

                    //this.lenght++
                
                }

                
                
                //const result = response.data
                //this.product = result
                //console.log(result)

            })

            

        }
  }
  

</script>


<template>
  <NavComponent/>
  <MainComponent/>
  <FooterComponent/>
</template>

<style lang="scss">
  @use'./style/general'
</style>
