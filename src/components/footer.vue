<template>
  <!-- Footer section with social media icons and newsletter sign-up -->
  <footer class="bg-neutral-900 text-center text-white">
    <div class="container px-6 pt-6">
      <!-- Newsletter sign-up form -->
      <div>
        <form action="">
          <div class="gird-cols-1 grid items-center justify-center gap-4 md:grid-cols-3">
            <div class="md:mb-6 md:ml-auto">
              <p class="">
                <strong>Sign up for our newsletter</strong>
              </p>
            </div>

            <!-- Newsletter sign-up input field -->
            <div class="relative md:mb-6" data-te-input-wrapper-init>
              <input
                type="text"
                class="peer block min-h-[auto] w-full rounded border-0 bg-transparent px-3 py-[0.32rem] leading-[1.6] text-neutral-200 outline-none transition-all duration-200 ease-linear focus:placeholder:opacity-100 data-[te-input-state-active]:placeholder:opacity-100 motion-reduce:transition-none dark:text-neutral-200 dark:placeholder:text-neutral-200 [&:not([data-te-input-placeholder-active])]:placeholder:opacity-0"
                id="exampleFormControlInput1"
                placeholder="Email address"
              />
              <label
                for="exampleFormControlInput1"
                class="pointer-events-none absolute left-3 top-0 mb-0 max-w-[90%] origin-[0_0] truncate pt-[0.37rem] leading-[1.6] text-neutral-200 transition-all duration-200 ease-out peer-focus:-translate-y-[0.9rem] peer-focus:scale-[0.8] peer-focus:text-neutral-200 peer-data-[te-input-state-active]:-translate-y-[0.9rem] peer-data-[te-input-state-active]:scale-[0.8] motion-reduce:transition-none dark:text-neutral-200 dark:peer-focus:text-neutral-200"
                >Email address
              </label>
            </div>

            <!-- Newsletter sign-up submit button -->
            <div class="mb-6 md:mr-auto">
              <button
                type="submit"
                class="inline-block rounded border-2 border-neutral-50 px-6 pb-[6px] pt-2 text-xs font-medium uppercase leading-normal text-neutral-50 transition duration-150 ease-in-out hover:border-neutral-100 hover:bg-neutral-500 hover:bg-opacity-10 hover:text-neutral-100 focus:border-neutral-100 focus:text-neutral-100 focus:outline-none focus:ring-0 active:border-neutral-200 active:text-neutral-200 dark:hover:bg-neutral-100 dark:hover:bg-opacity-10"
                data-te-ripple-init
                data-te-ripple-color="light"
              >
                Subscribe
              </button>
            </div>
          </div>
        </form>
      </div>

      <!-- Copyright information -->
      <div class="mb-6">
        <p>
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Sunt distinctio earum
          repellat quaerat voluptatibus placeat nam, commodi optio pariatur est quia
          magnam eum harum corrupti dicta, aliquam sequi voluptate quas.
        </p>
      </div>

      <!-- Links section -->
      <div class="grid md:grid-cols-2 lg:grid-cols-4">
        <div class="mb-6">
          <h5 class="mb-2.5 font-bold uppercase">Links</h5>

          <ul class="mb-0 list-none">
            <li>
              <a href="#!" class="text-white">Link 1</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 2</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 3</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 4</a>
            </li>
          </ul>
        </div>

        <div class="mb-6">
          <h5 class="mb-2.5 font-bold uppercase">Links</h5>

          <ul class="mb-0 list-none">
            <li>
              <a href="#!" class="text-white">Link 1</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 2</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 3</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 4</a>
            </li>
          </ul>
        </div>

        <div class="mb-6">
          <h5 class="mb-2.5 font-bold uppercase">Links</h5>

          <ul class="mb-0 list-none">
            <li>
              <a href="#!" class="text-white">Link 1</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 2</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 3</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 4</a>
            </li>
          </ul>
        </div>

        <div class="mb-6">
          <h5 class="mb-2.5 font-bold uppercase">Links</h5>

          <ul class="mb-0 list-none">
            <li>
              <a href="#!" class="text-white">Link 1</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 2</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 3</a>
            </li>
            <li>
              <a href="#!" class="text-white">Link 4</a>
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- Copyright section -->
    <div class="p-4 text-center" style="background-color: rgba(0, 0, 0, 0.2)">
      © 2023 Copyright:
      <a class="text-white" href="https://tailwind-elements.com/">Tailwind Elements</a>
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {};
  },
  mounted() {},
  name: "footerComponent",
};
</script>

<style lang="scss" scoped></style>
