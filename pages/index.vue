<template>
  <div class="h-screen w-full bg-gray-900 relative">
    <img
      src="@/assets/images/ceophoto2.png"
      alt="ceo photo"
      class="w-full h-screen object-center object-cover"
    />
    <div
      class="absolute bottom-0 px-4 pt-24 pb-10 w-full flex flex-col items-center justify-center mx-auto"
    >
      <h1
        class="overflow-hidden px-4 text-4xl font-bold tracking-widest rounded-md bg-gray-900 bg-opacity-50 text-blue-500 animate__animated animate__rubberBand animate__slow"
      >
        Ani Chukwuma
      </h1>
      <div
        class="overflow-hidden mt-2 py-2 px-4 bg-gray-200 bg-opacity-25 rounded-md shadow-xl"
      >
        <h1
          class="text-2xl text-center text-gray-200 relative overflow-hidden h-8 ceotyping"
        >
          <span class="text"></span>
          <span class="cursor">_</span>
        </h1>
      </div>
      <div>
        <n-link
          to="/about"
          class="block mt-8 px-4 py-21 text-gray-200 bg-gray-100 bg-opacity-25 rounded-md focus:outline-none focus:shadow-outline hover:text-blue-500"
        >
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-12 w-12 animate-pulse"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M13 5l7 7-7 7M5 5l7 7-7 7"
            />
          </svg>
        </n-link>
      </div>
    </div>
    <div class="absolute top-0 right-0 p-4 text-yellow-500">
      <SocialLinks />
    </div>
  </div>
</template>

<script>
export default {
  layout: "home",
  name: "Home",
  data() {
    return {
      words: [
        "I am an entreprenuer",
        "and the",
        "C. E. O. of",
        "XXXXXXXXXXXXX Nig. Ltd",
      ],
    };
  },
  mounted() {
    // ceo name
    gsap.from(".ceoname", {
      opacity: 0,
      duration: 3,
      x: 50,
      ease: "elastic",
    });

    // ceo typing
    gsap.from(".ceotyping", {
      opacity: 0,
      duration: 2,
      y: -50,
      delay: 2,
      ease: "elastic",
    });

    // cursor
    gsap.to(".cursor", {
      opacity: 0,
      ease: "power2.inOut",
      repeat: -1,
    });

    let boxTl = gsap.timeline();
    boxTl
      .to(".box", {
        duration: 1,
        width: "21vw",
        delay: 0.5,
        ease: "power4.inOut",
      })
      .from(".hi", {
        duration: 1,
        y: "7vw",
        ease: "power3.out",
        onComplete: () => masterTl.play(),
      })
      .to(".box", {
        duration: 1,
        height: "7vw",
        ease: "elastic.out",
      })
      .to(".box", {
        duration: 2,
        autoAlpha: 0.5,
        yoyo: true,
        repeat: -1,
        ease:
          "rough({ template: none.out, strength: 1, points: 20, taper: 'none', randomize: true, clamp: false})",
      });

    let masterTl = gsap.timeline({ repeat: -1 }).pause();
    this.words.forEach((word) => {
      let tl = gsap.timeline({
        repeat: 1,
        yoyo: true,
        repeatDelay: 2,
      });
      tl.to(".text", {
        duration: 1,
        text: word,
      });
      masterTl.add(tl);
    });

    // ceo photo
    gsap.from(".ceophoto", {
      opacity: 0,
      duration: 3,
      x: -50,
      ease: "elastic",
    });

    // about logo
    gsap.from(".about", {
      opacity: 0,
      duration: 1,
      y: 50,
      stagger: 0.6,
      ease: "Back.inOut",
    });

    // about business
    gsap.from(".business", {
      opacity: 0,
      duration: 1,
      y: 50,
      delay: 2,
      stagger: 0.6,
      ease: "Back.inOut",
    });

    // sample
    gsap.from(".sample", {
      opacity: 0,
      duration: 1,
      y: 50,
      delay: 3,
      stagger: 0.6,
      ease: "Back.inOut",
    });
  },
};
</script>