<template>
    <div tag="div" @before-leave="leave" class="loader-page">
        <p class="loading-text">

        </p>
        <div class="progress-bar">

        </div>

    </div>
</template>

<script setup>
import gsap from 'gsap'
import { TextPlugin } from 'gsap/all';
import { onMounted } from 'vue';

const leave=(el)=>{
    
}

gsap.registerPlugin(TextPlugin)
onMounted(()=>{
    const tl = gsap.timeline({})
    tl.from('.loader-page',{
        
        opacity:0,
        delay:1,
        duration:2,
    },'<').to('.loader-page',{
        
        delay:10,
        duration:4,
        
    }, '>')
    gsap.to('.loading-text', {
        text:'this showcase is sponsored by prometheus',
        duration:7,
        
        
    }, )
    
    
    
    // gsap.from('.progress-bar', {
    //     scale:'0',
    //     duration:2,
    // })
    
    gsap.to('.progress-bar', {
        width:'50%',
            scale:'1',
        duration:12,
    })
})
</script>

<style  scoped>
.loader-page{
    height: 100vh;
    position: absolute;
    background-color: #a6a9b3 ;
    width: 100vw;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

.loading-text{
    width: 50%;
    z-index: 40;
    height: 20%;
}
.progress-bar{
    width: 50%;
    z-index: 40;
    background-color: #121200;
    border-radius: 5px;
    height: 5px;
    transform: scaleX(0);
    transform-origin: left;
}
</style>