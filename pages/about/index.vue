<template>
  <div class="min-h-screen w-full bg-gray-900">
    <div class="sm:max-w-4xl mx-auto px-4 text-lg tracking-wide">
      <img
        src="@/assets/images/about.png"
        alt="about img"
        class="mx-auto about"
      />
      <h1
        class="text-center text-3xl uppercase tracking-widest text-yellow-500 inline border-b border-yellow-500"
      >
        About Me
      </h1>
      <p class="about mt-6 sm:text-2xl text-gray-200">
        <span class="font-bold">Ani Chukwuma</span> is a successfull
        entrepreneur and a contractor on various business fields with government
        agencies and private establishments. He is curently the Chief Executive
        Officer, CEO, of Xxxxxxxxx Nig. Ltd.
      </p>
      <p class="about pt-4 pb-8 sm:text-2xl text-gray-200">
        He is also lorem ipsum dolor sit amet consectetur adipisicing elit.
        Minus velit similique molestiae minima cum doloribus recusandae
        voluptates non corporis qui. Molestiae magnam est necessitatibus officia
        voluptate error iusto neque? Tenetur reiciendis eligendi quisquam a iure
        expedita libero eum delectus commodi?
      </p>
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