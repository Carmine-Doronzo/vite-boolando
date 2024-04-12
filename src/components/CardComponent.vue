<script>

    export default {
        
        props:{
            item:{
                type:Object,
                
            }
        },methods:{
            hearth(item){
                item.isInFavorites = !item.isInFavorites

            }
        }
        
    }
</script>

<template>
    
    
                        
        <img class="main-image" :src="`/img/${item.frontImage}`" alt="">
        <img class="second-image" :src="`/img/${item.backImage}`" alt="">
        
        <div class="line-height">
            
            <h6>{{ item.brand }}</h6>
            <h4>{{ item.name }}</h4>
            <div v-for="(discount,i) in item.badges" :key="i">
                <div v-if="discount.value === '-50%' && discount.type === 'discount'">
                    <h5  class="font-red display"> {{ (item.price-(item.price * 0.50)).toFixed(2) }} &euro;</h5>
                    <span class="line-through">{{ item.price }} &euro;</span>
                </div>
                
                <div v-else-if="discount.value === '-30%' && discount.type === 'discount'">
                    <h5  class="font-red display"> {{ (item.price-(item.price * 0.30)).toFixed(2) }} &euro;</h5>
                    <span class="line-through">{{ item.price }} &euro;</span>
                </div>
                <div v-else-if="item.badges.length < 2 && discount.type === 'tag'">
                    <span class="">{{ item.price }} &euro;</span>
                </div>     
            </div>
            
            
            
        </div>
        
        <div class="position">
            <span v-for="(badge,i) in item.badges" :key="i" :class="badge.type ==='discount'?'badge bg-red':'badge bg-green'">{{ badge.value }}</span>
            
        </div>
        
        <button @click="hearth(item)" :class="item.isInFavorites === true ? 'heart bg-white heart-color':'heart bg-white'">&hearts;</button>
        
    

    
</template>



<style lang="scss" scoped>

</style>