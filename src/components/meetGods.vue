<template>
    <div class="gods">
        <!--  -->
        <div class="box-1">
            <div class="zeus">
            <div class="img-box">
                <img src="../assets/images//Athena.webp" alt="">
            </div>
            <p>
                Athena was the goddess of reason, wisdom, and war. She famously sprung fully formed from the forehead of Zeus. A major figure in the Odyssey, in which she instructed Odysseus, she also guided Perseus and Heracles through their trials. The Parthenon was her chief temple in Athens, which is named in her honor. 
            </p>
        </div>
        </div>
        <div class="box-2">
            <div class="zeus">
            <div class="img-box">
                <img src="../assets/images/Aphrodite.webp" alt="">
            </div>
            <p>
                Aphrodite was the goddess of love, sex, and beauty. Unsurprisingly for a love goddess, she was said to have emerged from the foam generated when the severed testicles of her father, Uranus, were thrown into the sea by his son, the Titan Cronus.
            </p>
        </div>
        </div>
        <div class="box-3">
            <div class="zeus">
            <div class="img-box">
                <img src="../assets/images/Apollo-Belvedere-copy-original-Roman-Leochares-Greek.webp" alt="">
            </div>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Numquam non, aspernatur deleniti rem est
                 officia sint excepturi nam veniam officiis dicta, aut quod, harum 
                beatae tenetur mollitia dolorem praesentium ducimus.
                Lorem ipsum, dolor sit amet consectetur adipisicing elit. Sint, qui. Nostrum sit eos suscipit unde voluptates eligendi quibusdam eaque ullam asperiores doloribus repellat voluptatibus a, sint nihil vitae ut qui exercitationem explicabo eum fugit. Voluptatibus debitis voluptates perspiciatis commodi quasi?
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

    onMounted(()=>{
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
            start:'top top',
            end:'+=500',
            // markers:true,
            scrub:true,
            pin:true,anticipatePin:true,
            // pinSpacing:false
            snap:1/3

        })
    })
</script>

<style scoped>
.gods{
    height: 100vh;
    padding: 5vh 0 0;
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
    background:pink;
    position: absolute;
    width: 100%;
    height: 100%;
    /* z-index:50; */
background-color: #ddd;

}
.box-3{
background-color: #a6a9b3;
    
    position: absolute;

    width: 100%;
    height: 100%;
}
.zeus{
    display: flex;
    width: 100%;
    height: 100%;
}
.img-box{
    
    width: 100%;
    height: 100%;
}
img{
    width: 90%;
}
.zeus:nth-of-type(1)>p{
    align-self: center;
    text-align: left;
    flex-basis: 50%;
    width: 100%;
    background-color: #121212;
    color:#fdfdfd
}

</style>