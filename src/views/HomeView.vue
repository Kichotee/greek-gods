<template>
	<div class="home">
		<h2 class="title">The Gods of old</h2>
		<div class="home-content">
			<div class="img-header-box">
				<img
					class="poseidon"
					src="../assets/images/Artemis-huntress-Paris-Louvre.webp"
					alt=""
				/>
			</div>
			<div class="img-header-box-2">
				<img
					class="atena"
					src="../assets/images/Ares-Rome-National-Roman-Museum.webp"
					alt=""
				/>
			</div>
			<div class="img-header-box-3">
				<img
					class="ares"
					src="../assets/images/Ares-Rome-National-Roman-Museum.webp"
					alt=""
				/>
			</div>
			<h2 class="content-text">
				Lorem ipsum dolor sit amet consectetur
				adipisicing elit. Ducimus earum similitude
				consectetur ut officiis quia eum eveniet
				doloribus quidem error?
			</h2>
		</div>
	</div>
	<!-- <meetGods /> -->
</template>

<script setup>
	// @ is an alias to /src
	import meetGods from "@/components/meetGods.vue";
	import gsap from "gsap";
	import { onMounted } from "vue";

	name: "HomeView",
		onMounted(() => {
			gsap.from(".home", {
				y: "-150%",
				opacity: 0,
				duration: 1,
			})
      gsap.from(
				".img-header-box",
				{
					opacity: 0,
          y:'-100%',
					duration: 1.5,
					delay: 0.25,
          // ease:'bounce'',
				},
				">"
        );
        gsap.from(
          ".img-header-box-2",
          {
          y:'100%',
					opacity: 0,
					duration: 1.5,
					delay: 0.25,
          ease:'power4.out'
				},
				">"
			);
        gsap.from(
          ".img-header-box-3",
          {
          x:'100%',
					opacity: 0,
					duration: 1.5,
					delay: 0.25,
          ease:'power2.out'
				},
				">"
			);
        gsap.from(
          ".content-text",
          {
          y:'-400%',
					// opacity: 0,
					duration: 1.5,
					delay: 0.25,
          ease:'bounce'
				},
				">"
			);
		});
</script>

<style scoped>
	@font-face {
		font-family: roxette;
		src: url(../assets/Roxete.ttf);
	}
	.home {
		height: 100vh;
		overflow: hidden;
		background-color: #a6a9b3;
	}
	.home-content {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		grid-template-rows: repeat(2, 1fr);
		align-items: end;
		width: 100%;
		height: 100%;
	}
	.title {
		font-size: 5em;
		color: antiquewhite;
		z-index: 20;
		font-family: roxette;
		position: absolute;
		left: 50%;
		translate: -50% 0%;
	}
	.content-text {
	}

	.img-header-box {
		grid-column: 1;
		grid-row: 1 / -1;
		/* background-color: #fff; */

		/* color: #f6aa8c; */
		align-self: center;
	}
	.img-header-box-2 {
		grid-column: 2;
		grid-row: 1 / -1;
		align-self: center;
		/* background-color: #fff; */

		/* color: #f6aa8c; */
	}
	.img-header-box-3 {
		grid-column: 3;

		/* background-color: #fff; */

		/* color: #f6aa8c; */
	}
	.poseidon {
		width: 60%;
	}

	.atena {
		mix-blend-mode: multiply;
		width: 90%;
	}
	.ares {
		width: 40%;
		height: 30%;
	}
	h2 {
		grid-column: 3;
		grid-row: 1;
		text-align: left;
		font-family: roxette;
	}
</style>
