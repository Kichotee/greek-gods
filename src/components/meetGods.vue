<template>
    <div class="gods" >
        <h4 >Scroll down</h4 >
        <!--  -->
        <div class="box box-1" >
            <div class="zeus">
                <transition @enter="imageEnter">
                    <div class="img-box">
                        <img id="gods" src="../assets/images/Ares-Rome-National-Roman-Museum.webp" alt="">
                    </div>
                </transition>
            <p>
                Ares was the god of bloodlust. (His half-sister Athena represented the more "noble" aspects of combat and civil conduct during war.) Though his fellow deities weren’t particularly fond of him, the Spartans had no problems, er, donating some prisoners of war to his worship. And sacrificing dogs…yeah, that’s right, Ares liked dead puppies
            </p>
        </div>
        </div>
        <div class="box box-2">
            <div class="zeus">
            <div class="img-box">
                <img src="../assets/images/Athena.webp" alt="">
            </div>
            <p>
                Athena was the goddess of reason, wisdom, and war. She famously sprung fully formed from the forehead of Zeus. A major figure in the Odyssey, in which she instructed Odysseus, she also guided Perseus and Heracles through their trials. The Parthenon was her chief temple in Athens, which is named in her honor. 
            </p>
        </div>
        </div>
        <div class="box box-3">
            <div class="zeus">
            <div class="img-box">
                <img src="../assets/images/Dionysus.webp" alt="">
            </div>
            <p>
                Dionysus was a son of Zeus born to a mortal mother. When Zeus accidentally killed her, he sewed the young Dionysus into his thigh and, when the young god emerged, passed him to the care of the maenads. The cult of Dionysus revolved around intoxication, sex, and savage ritual sacrifice. He was often symbolized by a bull due to his association with the sacrificial animal. Elements of his character are seen in the Roman god of wine, Bacchus.
            </p>
        </div>
        </div>
    </div>
</template>

<script setup>
    import gsap from 'gsap';
    import ScrollTrigger from 'gsap/ScrollTrigger';
    
import { onMounted } from 'vue';
gsap.defaults({duration:2})

    gsap.registerPlugin(ScrollTrigger)
    const imageEnter=(el)=>{
        gsap.from(el,{
            opacity:0
        })
    }
    
    onMounted(()=>{
        const images= gsap.utils.toArray('img')

        gsap.from(images,{
                opacity:0,
                duration:2,
                
            })
          
    const    tl=gsap.timeline({})

        tl.from('.box-1',{
            x:'-100%',
            duration:2,
        }).from('.box-2',{
            x:'100%',
            duration:2,
        }).from('.box-3',{
            x:'-100%',
            duration:2,
        })

        ScrollTrigger.create({
            animation:tl,
            trigger:'.gods',
            start:`top top`,
            end:'+=800',
            // markers:true,
            scrub:true,
            pin:true,
            anticipatePin:true,
            // pinSpacing:false
            snap:1/3

        })
        gsap.from('.box-1',{
            opacity:0,
            duration:5
        })

    })
</script>

<style scoped>
.gods{
    height: 100vh;
    background-color: #a6a9b3;
    overflow: hidden;
  
  position: relative;
    
}
.box-1{
    position: absolute;
    width: 100%;
    height: 100%;
background-color: #a6a9b3;
    
}
.box-2{

    position: absolute;
    width: 100%;
    height: 100%;
    /* z-index:50; */
background-color: #a6a9b3;

}
.box-3{
background-color: #a6a9b3;
    
    position: absolute;

    width: 100%;
    height: 100%;
		color: antiquewhite;

}
.zeus{
    display: flex;
    width: 100%;
    height: 100%;
    position:relative
}
.img-box{
    
    width: 100%;
    height: 100%;
}
img{
    width: 100%;
    height: 100%;
    object-fit: contain;
    
}
p{
    align-self: center;
    text-align: left;
    flex-basis: 50%;
    width: 100%;
    color:#fdfdfd;
    padding:0.5em;
}
p:nth-of-type(2){
    color: #121212;
}

</style>