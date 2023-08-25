<template>
  <main class="">
    <div class="grid grid-cols-2 mt-[20rem] gap-10">
      <section class="grid gap-10">
        <section class="p-7 w-fit flex">
          <div class="pr-10 grid gap-10">
            <h1 class="text-4xl font-bold">
              Websites that are easy to understand
            </h1>
            <p class="text-xl">
              If you’re not happy with the design after the first draft, I’ll
              refund your deposit, no questions asked.
            </p>
          </div>
        </section>
        <section class="p-7 w-fit">
          <div class="pr-10 grid gap-10">
            <h1 class="text-4xl font-bold">
              Websites that are easy to understand
            </h1>
            <p class="text-xl">
              If you’re not happy with the design after the first draft, I’ll
              refund your deposit, no questions asked.
            </p>
          </div>
        </section>
        <section class="p-7 w-fit">
          <div class="pr-10">
            <h1 class="text-4xl font-bold">
              Websites that are easy to understand
            </h1>
            <p class="text-xl">
              If you’re not happy with the design after the first draft, I’ll
              refund your deposit, no questions asked.
            </p>
          </div>
        </section>
      </section>
      <div class="border h-[20rem] w-full"></div>
    </div>
    <div class="scroller grid bg-red-200 grid-cols-2 pb-[10rem] gap-10">
      <section class="grid gap-20 scrollable border-2 h-fit">
        <section class="p-7 h-fit scrollable1 w-fit flex">
          <div class="pr-10 grid gap-10">
            <h1 class="text-4xl font-bold">
              Websites that are easy to understand
            </h1>
            <p class="text-xl">
              If you’re not happy with the design after the first draft, I’ll
              refund your deposit, no questions asked.
            </p>
          </div>
        </section>
        <section class="p-7 h-fit scrollable1 w-fit">
          <div class="pr-10 grid gap-10">
            <h1 class="text-4xl font-bold">
              Websites that are easy to understand
            </h1>
            <p class="text-xl">
              If you’re not happy with the design after the first draft, I’ll
              refund your deposit, no questions asked.
            </p>
          </div>
        </section>
        <section class="h-fit scrollable1 p-7 w-fit">
          <div class="pr-10">
            <h1 class="text-4xl font-bold">
              Websites that are easy to understand
            </h1>
            <p class="text-xl">
              If you’re not happy with the design after the first draft, I’ll
              refund your deposit, no questions asked.
            </p>
          </div>
        </section>
      </section>
      <div
        class="pinned-panel sticky top-[25rem] self-start bg-blue-300 h-[20rem] w-full"
      >
        <img
          src="/image0.jpg"
          alt=""
          class="w-full border-2 h-full object-cover"
        />
        <img
          src="/image1.jpg"
          alt=""
          class="w-full border-2 h-full object-cover"
        />
        <img
          src="/image2.jpg"
          alt=""
          class="w-full border-2 h-full object-cover"
        />
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import { onMounted } from "vue";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/dist/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
  const imageElements = document.querySelectorAll(".pinned-panel img");
  gsap.utils.toArray(".scrollable1").forEach((section, index) => {
    const pinnedPanelImg = document.querySelector(".pinned-panel img");
    gsap.fromTo(
      pinnedPanelImg,
      { opacity: 0 }, // Start with opacity 0
      {
        scrollTrigger: {
          // @ts-ignore
          trigger: section,
          start: "top center+=300px",
          // end: "bottom center+=500px",
          onEnter: () => {
            imageElements[index].classList.toggle("show");
            console.log(index, "check the current section index here");
          },
          onLeaveBack: () => {
            imageElements[index].classList.toggle("show");
            console.log(index, "check the current section index here");
          },
        },
        opacity: 1, // Reset opacity for next animation
      }
    );
  });
});
</script>

<style lang="css">
@import "./main.css";
</style>
