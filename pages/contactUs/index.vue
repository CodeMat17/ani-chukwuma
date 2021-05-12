<template>
  <div class="w-full min-h-screen bg-yellow-100">
    <div class="py-12 px-2 sm:max-w-sm mx-auto">
      <div class="border py-6 px-4 bg-white rounded-xl shadow-2xl">
        <h1
          class="py-4 text-center text-2xl font-bold uppercase tracking-wider"
        >
          Contact Me
        </h1>
        <div class="">
          <form class="space-y-4">
            <div>
              <label>Name</label>
              <input
                type="text"
                name="name"
                id="name"
                placeholder="Enter Your Name"
                v-model="name"
                class="w-full border rounded-md"
              />
            </div>
            <div>
              <label>Phone No.</label>
              <input
                type="tel"
                name="phone"
                id="tel"
                placeholder="Phone No."
                class="w-full border rounded-md"
              />
            </div>
            <div>
              <label>Subject</label>
              <input
                type="text"
                name="subject"
                id="subject"
                placeholder="Subject"
                class="w-full border rounded-md"
              />
            </div>
            <div>
              <label>Message</label>
              <textarea
                name="message"
                id="message"
                cols="15"
                rows="10"
                placeholder="Enter Your Message Here"
                class="w-full border rounded-md"
              ></textarea>
            </div>
            <button
              type="submit"
              class="p-3 rounded-lg uppercase w-full bg-gray-800 text-gray-200"
            >
              Not Functional Yet
            </button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>