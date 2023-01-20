<template>
    <div class="pantheon-container">



        <div
            class="pantheon box-row"
            @click="ToggleClass"
            :class="{ 'box-col': col_mode }"
        >
    
            <div class="box box-1">
            
                <img src="../assets/images/acropolis-2725918_1920.jpg" alt="">
            </div>
            <div class="box box-2">
                <img src="../assets/images/acropolis-2725918_1920.jpg" alt="">
                
            </div>
            <div class="box box-3">
                <img src="../assets/images/acropolis-2725918_1920.jpg" alt="">
                
            </div>
    
            <p>
                just click, you'd see more.
            </p>
            <!-- <img class="img-2" src="../assets/images/acropolis-2725918_1920.jpg" alt="">
            <img class="img-3" src="../assets/images/acropolis-2725918_1920.jpg" alt=""> -->
        </div>
    </div>
</template>

<script setup>
	import gsap from "gsap";
	import ScrollTrigger from "gsap/ScrollTrigger";
	import Flip from "gsap/Flip";
	import { onMounted, ref, nextTick } from "vue";
	const col_mode = ref(false);
	gsap.registerPlugin(ScrollTrigger, Flip);
    let pantheon= document.getElementsByClassName('pantheon')
	
	let state = Flip.getState(".pantheon,box");
	// const tl = gsap.timeline({});
	onMounted(() => {
        pantheon= document.getElementsByClassName('pantheon')
		state = Flip.getState(".pantheon, .box");
	});
    let changePos=ref(null)
	const ToggleClass = () => {
		col_mode.value = !col_mode.value;
		nextTick(() => {
         changePos.value=   Flip.from(state, {
                duration: 5,
                ease: "power2.out",
                simple: true,
                absolute:true,
                stagger:.1
            });
		});
	};
   
</script>

<style scoped>

.pantheon-container{

    position: relative;
}
	.pantheon {
		height: 100vh;
		/* width: 90vw; */
		/* overflow: hidden; */
		background-color: #a6a9b3;
    position: relative;

	}
	.box-row {
		display: flex;
		flex-direction: row;
        /* height: 100%; */
	}
	.box-col {
		display: flex;
		flex-direction: column;
	}
    .box{
        display:grid;
        place-items: center;
        flex-basis: 33.3%;
    position: relative;

    }
	img {
		object-fit: cover;
		/* width: 50%; */
		filter: grayscale(80%);
        width: 80%;
	}
   
	.box-1 {
		grid-column: 1;
		grid-row: 1;

		
		background-color: #ffffff04;
	}
	.box-2 {
       
        background-color: #ffffff9a;
		
		
	}
	.box-3 {
        background-color: #fffffffa;
		
		
	}
    p{
        position: absolute;

    }
</style>
