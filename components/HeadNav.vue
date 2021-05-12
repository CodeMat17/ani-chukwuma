<template>
  <div class="flex items-center justify-between px-4 py-2 bg-gray-900">
    <div class="textFont text-yellow-500 text-3xl tracking-widest">
      Ani Chukwuma
    </div>
    <div class="hidden md:block space-x-4 uppercase text-gray-200">
      <n-link to="/">Home</n-link>
      <n-link to="/about">About</n-link>
      <n-link to="/company">Company</n-link>
    </div>
    <div class="md:hidden">
      <button
        @click="showMenu = !showMenu"
        class="text-yellow-500 focus:outline-none focus:shadow-outline rounded-md"
      >
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-8 w-8"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
        >
          <path
            v-if="!showMenu"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16m-7 6h7"
          />

          <path
            v-if="showMenu"
            class="text-white"
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M6 18L18 6M6 6l12 12"
          />
        </svg>
      </button>

      <div
        v-if="showMenu"
        class="absolute right-0 w-full h-auto p-4 flex justify-end"
      >
        <div
          class="px-8 w-auto h-auto flex flex-col justify-end bg-white border rounded-xl shadow-2xl py-6"
        >
          <div
            class="flex flex-col space-y-6 text-gray-800 uppercase text-xl font-semibold tracking-wider"
          >
            <button
              @click="homeButt"
              class="font-semibold uppercase tracking-wider"
            >
              Home
            </button>
            <button
              @click="aboutButt"
              class="font-semibold uppercase tracking-wider"
            >
              About Me
            </button>
            <button
              @click="companyButt"
              class="font-semibold uppercase tracking-wider"
            >
              My Company
            </button>
          </div>
          <br />
          <h1 class="italic text-gray-500 text-xl">Contact Us</h1>
          <div
            class="flex items-center justify-between text-gray-800 space-x-6"
          >
            <button @click="contactUsButt">
              <svg class="w-8 h-8 hover:opacity-50" viewBox="0 0 24 24">
                <path
                  fill="currentColor"
                  d="M19.07 13.88L13 19.94V22H15.06L21.12 15.93M22.7 13.58L21.42 12.3C21.32 12.19 21.18 12.13 21.04 12.13C20.89 12.14 20.75 12.19 20.65 12.3L19.65 13.3L21.7 15.3L22.7 14.3C22.89 14.1 22.89 13.78 22.7 13.58M11 18H4V8L12 13L20 8V10H22V6C22 4.9 21.1 4 20 4H4C2.9 4 2 4.9 2 6V18C2 19.1 2.9 20 4 20H11V18M20 6L12 11L4 6H20Z"
                />
              </svg>
            </button>
            <a href="https://twitter.com" target="_blank">
              <svg class="w-8 h-8" viewBox="0 0 24 24">
                <path
                  fill="currentColor"
                  d="M22.46,6C21.69,6.35 20.86,6.58 20,6.69C20.88,6.16 21.56,5.32 21.88,4.31C21.05,4.81 20.13,5.16 19.16,5.36C18.37,4.5 17.26,4 16,4C13.65,4 11.73,5.92 11.73,8.29C11.73,8.63 11.77,8.96 11.84,9.27C8.28,9.09 5.11,7.38 3,4.79C2.63,5.42 2.42,6.16 2.42,6.94C2.42,8.43 3.17,9.75 4.33,10.5C3.62,10.5 2.96,10.3 2.38,10C2.38,10 2.38,10 2.38,10.03C2.38,12.11 3.86,13.85 5.82,14.24C5.46,14.34 5.08,14.39 4.69,14.39C4.42,14.39 4.15,14.36 3.89,14.31C4.43,16 6,17.26 7.89,17.29C6.43,18.45 4.58,19.13 2.56,19.13C2.22,19.13 1.88,19.11 1.54,19.07C3.44,20.29 5.7,21 8.12,21C16,21 20.33,14.46 20.33,8.79C20.33,8.6 20.33,8.42 20.32,8.23C21.16,7.63 21.88,6.87 22.46,6Z"
                />
              </svg>
            </a>
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
      showMenu: false,
    };
  },
  methods: {
    homeButt() {
      this.$router.push("/");
      this.showMenu = false;
    },
    aboutButt() {
      this.$router.push("/about");
      this.showMenu = false;
    },
    companyButt() {
      this.$router.push("/company");
      this.showMenu = false;
    },
    contactUsButt() {
      this.$router.push("/contactUs");
      this.showMenu = false;
    },
  },
};
</script>
<style scoped>
.textFont {
  font-family: "Dancing Script";
}
</style>