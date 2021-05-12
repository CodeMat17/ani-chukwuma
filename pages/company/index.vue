<template>
  <div class="min-h-screen w-full bg-gray-900">
    
    
    <div class="sm:max-w-4xl mx-auto py-10 px-4 text-lg tracking-wide">
        <img
          src="@/assets/images/ideas.png"
          alt="about img"
          class="h-48 mx-auto business"
        />
        <h1
        class="mt-4 text-center text-3xl uppercase tracking-widest text-yellow-500 inline border-b border-yellow-500"
      >
        My Company
      </h1>
      <p class="mt-6 business sm:text-2xl text-gray-200">
        <span class="font-bold">Xxxxxxxxx Nig. Ltd</span>
        is a business of repute and deals on Lorem ipsum dolor sit amet
        consectetur adipisicing elit. Minus ad, animi numquam impedit sint rem,
        obcaecati repellendus harum exercitationem vel vero quia fugit ea.
        Consequatur, doloribus. Sed quas eligendi omnis.
      </p>
      <p class="mt-4 business sm:text-2xl text-gray-200">See samples below</p>
      <div class="mt-2 sm:grid sm:grid-cols-2 md:grid-cols-3 sm:gap-4">
        <div class="sample my-6 border bg-white shadow-xl rounded-lg overflow-hidden hover:bg-gray-800 hover:text-gray-200">
          <img
            src="@/assets/images/decorbed.jpg"
            alt="beddings"
            class="w-full object-cover object-center"
          />
          <div class="p-4 flex items-center justify-between">
            <p class="font-semibold tracking-wider">Beddings</p>
            <a
              href="#"
              class="text-sm text-center tracking-wider shadow-lg p-1 rounded-lg bg-yellow-500"
              >See more</a
            >
          </div>
        </div>
        <div class="sample my-6 border bg-white shadow-xl rounded-lg overflow-hidden hover:bg-gray-800 hover:text-gray-200">
          <img
            src="@/assets/images/decorcurtains.jpg"
            alt="beddings"
            class="w-full object-cover object-center"
          />
          <div class="p-4 flex items-center justify-between">
            <p class="font-semibold tracking-wider">Curtains</p>
            <a
              href="#"
              class="text-sm text-center tracking-wider shadow-lg p-1 rounded-lg bg-yellow-500"
              >See more</a
            >
          </div>
        </div>
        <div class="sample my-6 border bg-white shadow-xl rounded-lg overflow-hidden hover:bg-gray-800 hover:text-gray-200">
          <img
            src="@/assets/images/decorfurniture.jpg"
            alt="beddings"
            class="w-full object-cover object-center"
          />
          <div class="p-4 flex items-center justify-between">
            <p class="font-semibold tracking-wider">Furnitures</p>
            <a
              href="#"
              class="text-sm text-center tracking-wider shadow-lg p-1 rounded-lg bg-yellow-500"
              >See more</a
            >
          </div>
        </div>
      </div>
    </div>
  
  </div>
</template>

<script>
export default {
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
      ease: 'elastic'
    });

    // ceo typing
    gsap.from(".ceotyping", {
      opacity: 0,
      duration: 2,
      y: -50,
      delay: 2,
      ease: 'elastic'
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
      ease: 'elastic'
    });

     // about logo
    gsap.from(".about", {
      opacity: 0,
      duration: 1,
      y: 50,
      stagger: 0.6,
      ease: 'Back.inOut'
    });

    // about business
    gsap.from(".business", {
      opacity: 0,
      duration: 1,
      y: 50,
      delay:2,
      stagger: 0.6,
      ease: 'Back.inOut'
    });

    // sample
    gsap.from(".sample", {
      opacity: 0,
      duration: 1,
      y: 50,
      delay:3,
      stagger: 0.6,
      ease: 'Back.inOut'
    });
  },
};
</script>