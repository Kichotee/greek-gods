<template>
    <div tag="div" @before-leave="leave" class="loader-page">
        <p class="loading-text">
            This showcase is sponsored by prometheus
        </p>
        <div class="progress-bar">

        </div>
        <div class="loading-number">
            
        </div>

    </div>
</template>

<script setup>
import gsap from 'gsap'
import { TextPlugin } from 'gsap/all';
import { onMounted, ref } from 'vue';


gsap.registerPlugin(TextPlugin)
onMounted(()=>{
    let counter = {
        value:ref(0)
    }
    const tl = gsap.timeline({})
    tl.from('.loader-page',{
        
        opacity:0,
        delay:1,
        duration:2,
    },'<').to('.loader-page',{
        
        delay:10,
        duration:4,

        
    }, '>')
   
    // gsap.to('.loading-text', {
    //     text:'this showcase is sponsored by prometheus',
    //     duration:7,
        
        
        
    // }, )
    let loadingNumber=document.querySelector('.loading-number')
    gsap.to(counter, {
        value:Math.random() * 1000 ,
        duration:7,
        ease:'Power3.out' ,
        onUpdate:()=>{
            loadingNumber.innerText= 'here we are in '+' '+ Math.round(counter.value) + ' BC'
        }
        
        
        
    }, )
  

    
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
p{
    animation: text-shake 0.5s linear infinite;
}
/* @keyframes text-shake {
    0%{
        translate:0% 0;
        rotate:0 0;
    }
    25%{
        translate:5% 0;
    
    }
    75%{
        translate:-5% 0;
      
    }
    100%{
        rotate:0 0;
        translate:0% 0;
    }
    
    
} */
</style>