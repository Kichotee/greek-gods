<template>
    <div class="pantheon-container">



        <div
            class="pantheon box-row"
            @click="ToggleClass"
            :class="{ 'box-col': col_mode }"
        >
    
            <div class="box box-1">
            
                <div class="">

                    <h5>The partheon</h5>
                    <p class="temple-details">
                        Located in the hills of the acropolis in athens, this temple is dedicated to Athena
                    </p>
                </div>
                <img src="../assets/images/acropolis-2725918_1920.jpg" alt="">
            </div>
            <div class="box box-2">
                <div class="box-2-text">
    
                    <h5>The pantheon</h5>
                    <p class="temple-details">
                        Located in the hills of the acropolis in athens, this temple is dedicated to Athena
                    </p>
                </div>
                <img src="../assets/images/Mount-Olympus-Greece.webp" alt="">
                
            </div>
            <div class="box box-3">
                <div class="">
    
                    <h5>The temple of Hera</h5>
                    <p class="temple-details">
                        Located in the hills of the acropolis in athens, this temple is dedicated to Athena
                    </p>
                </div>
                <img src="../assets/images/Ancient-Temple-of-Goddess-Hera-Olympia.-min.jpg" alt="">
                
            </div>
            <div class="box box-4">
                <div class="">
    
                    <h5>The temp;e of poseidon</h5>
                    <p class="temple-details">
                        Located in the hills of the acropolis in athens, this temple is dedicated to Athena
                    </p>
                </div>
                <img src="../assets/images/Temple-of-Poseidon-at-Sounion-Greece-during-summer-sunset-min.jpg" alt="">
                
            </div>
    
            <p class="directives">
                Just click, you'd see more...or less
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
          Flip.from(state, {
                duration: .5,
                simple: true,
                absolute:true,
                stagger:.25
            });
		});
	};
   
</script>

<style scoped>

.pantheon-container{

    position: relative;
    /* overflow-x: scroll; */
}
	.pantheon {
        margin: 2.5% 0;
		height: max-content;
        max-width:100vw;
		background-color: #a6a9b3;
    position: relative;
	}
	.box-row {
		display: grid;
		flex-direction: row;
        grid-template-columns:repeat(4, 1fr);
        grid-template-rows:repeat(2, 1fr)
        /* height: 100%; */
	}
	.box-col {
		display: flex;
		flex-direction: column;
	}
    .box{
        display:grid;
        place-items: center;
        grid-template-columns: repeat(2,1fr);
        flex-basis: 33.3%;
        height: 60vh;
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

		
        grid-row: 1;
        grid-column: 2;
		background-color: #ffffffd4;
	}
	.box-2 {
       
        background-color: #ffffff9a;
		
        grid-row: 1;
        grid-column: 4;
		
	}
     .box-1-text{
       
    }
	.box-3 {
        background-color: #fffffffa;
		
        grid-row: 2;
        grid-column: 1;
		
	}
	.box-4 {
        background-color: #ddddddfa;
        grid-row: 2;
        grid-column: 3;
		
		
	}
    .temple-details{
        padding:0 2.5vh;
        font-family: roxette;
    }
    .directives{
        font-family: roxette;
        font-weight: 700;
        position: absolute;
        left: 60%;
        translate: -50% 0;

    }
</style>
