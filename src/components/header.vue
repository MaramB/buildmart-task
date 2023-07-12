<template>
  <div class="black-header flex">
    <div class="heading1">
      <p>
        Mon-Thu:
        <span> {{ " " }}9:00 AM - 5:30 PM</span>
      </p>
    </div>

    <div class="heading2">
      <p>
        Visit our showroom in 1234 Street Adress City Address, 1234
        <span>Contact Us</span>
      </p>
    </div>
  </div>

  <div class="navbar">
    <!-- Main navigation container -->
    <nav
      class="flex-no-wrap relative flex w-full items-center justify-between bg-[#FBFBFB] py-2 shadow-md shadow-black/5 dark:bg-neutral-600 dark:shadow-black/10 lg:flex-wrap lg:justify-start lg:py-4"
      data-te-navbar-ref
    >
      <div class="flex w-full flex-wrap items-center justify-between px-3">
        <!-- Hamburger button for mobile view -->
        <button
          class="block border-0 bg-transparent px-2 text-neutral-500 hover:no-underline hover:shadow-none focus:no-underline focus:shadow-none focus:outline-none focus:ring-0 dark:text-neutral-200 lg:hidden"
          type="button"
          data-te-collapse-init
          data-te-target="#navbarSupportedContent12"
          aria-controls="navbarSupportedContent12"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <!-- Hamburger icon -->
          <span class="[&>svg]:w-7">
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              fill="currentColor"
              class="h-7 w-7"
            >
              <path
                fill-rule="evenodd"
                d="M3 6.75A.75.75 0 013.75 6h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 6.75zM3 12a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75A.75.75 0 013 12zm0 5.25a.75.75 0 01.75-.75h16.5a.75.75 0 010 1.5H3.75a.75.75 0 01-.75-.75z"
                clip-rule="evenodd"
              />
            </svg>
          </span>
        </button>

        <!-- Collapsible navigation container -->
        <div
          
          class="!visible hidden flex-grow basis-[100%] items-center lg:!flex lg:basis-auto"
          id="navbarSupportedContent12"
          data-te-collapse-item
        >
          <!-- Logo -->
          <a
            class="mb-4 ml-2 mr-5 mt-3 flex items-center text-neutral-900 hover:text-neutral-900 focus:text-neutral-900 dark:text-neutral-200 dark:hover:text-neutral-400 dark:focus:text-neutral-400 lg:mb-0 lg:mt-0"
            href="#"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="85"
              height="69"
              viewBox="0 0 85 69"
              fill="none"
            >
              <path
                d="M42.0331 13.9454L25.2969 23.8637V36.0708L42.0331 45.9891L55.4588 38.3596V41.9836L42.0331 49.9946L25.2969 39.8855V44.2725L42.0331 54L58.7693 44.2725V32.0653L45.3435 39.8855V36.0708L58.7693 28.0599V23.8637L42.0331 13.9454Z"
                fill="#0156FF"
              />
            </svg>
          </a>
          <!-- Left navigation links -->
          <ul
            class="list-style-none mr-auto flex flex-col pl-0 lg:flex-row"
            data-te-navbar-nav-ref
          >
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <!-- Laptops link -->
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-zinc-400"
                href="#"
                data-te-nav-link-ref
                >Laptops</a
              >
            </li>
            <!-- Desktop PCs link -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-neutral-400"
                href="#"
                data-te-nav-link-ref
                >Desktop PCs</a
              >
            </li>
            <!-- Networking Devices link -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-neutral-400"
                href="#"
                data-te-nav-link-ref
                >Networking Devices</a
              >
            </li>
            <!-- Printers & Scanners link -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-neutral-400"
                href="#"
                data-te-nav-link-ref
                >Printers & Scanners</a
              >
            </li>
            <!-- PC Parts link -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-neutral-400"
                href="#"
                data-te-nav-link-ref
                >PC Parts</a
              >
            </li>
            <!-- All Other Products link -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-neutral-400"
                href="#"
                data-te-nav-link-ref
                >All Other Products</a
              >
            </li>
            <!-- Repairs link -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <a
                class="text-neutral-500 transition duration-200 hover:text-neutral-700 hover:ease-in-out focus:text-neutral-700 disabled:text-black/30 motion-reduce:transition-none dark:text-neutral-200 dark:hover:text-neutral-300 dark:focus:text-neutral-300 lg:px-2 [&.active]:text-black/90 dark:[&.active]:text-neutral-400"
                href="#"
                data-te-nav-link-ref
                >Repairs</a
              >
            </li>
            <!-- Our Deals button -->
            <li class="mb-4 lg:mb-0 lg:pr-2" data-te-nav-item-ref>
              <button type="button" class="our-deals">Our Deals</button>
            </li>
          </ul>
        </div>

        <!-- Right elements -->
        <div class="relative flex items-center" style="margin-right: 4%;">
          <!-- Search Icon -->
          <a
            class="mr-4 text-secondary-500 transition duration-200 hover:text-secondary-400 hover:ease-in-out focus:text-secondary-400 disabled:text-black/30 motion-reduce:transition-none"
            href="#"
          >
            <span class="[&>svg]:w-5">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="19"
                height="19"
                viewBox="0 0 19 19"
                fill="none"
              >
                <path
                  d="M4.95072 2.99141C3.79204 4.14838 3.11812 5.70363 3.06631 7.34023C3.0145 8.97682 3.58868 10.5716 4.67185 11.7995C5.75503 13.0275 7.26567 13.7962 8.89594 13.9491C10.4965 14.0991 12.0941 13.6444 13.3749 12.6766L16.7061 16.0085L16.7061 16.0085C16.789 16.0914 16.8873 16.1571 16.9955 16.2019C17.1038 16.2468 17.2198 16.2698 17.3369 16.2698C17.4541 16.2698 17.5701 16.2468 17.6783 16.2019C17.7866 16.1571 17.8849 16.0914 17.9678 16.0085C18.0506 15.9257 18.1163 15.8274 18.1611 15.7191C18.206 15.6109 18.229 15.4949 18.229 15.3777C18.229 15.2606 18.206 15.1446 18.1611 15.0363C18.1163 14.9281 18.0506 14.8298 17.9678 14.7469L17.9677 14.7469L14.636 11.416C15.6013 10.135 16.0539 8.53846 15.903 6.93943C15.7493 5.31054 14.9808 3.80139 13.7539 2.719C12.5269 1.63662 10.9337 1.06232 9.29838 1.11292C7.66303 1.16352 6.10838 1.83523 4.95072 2.99141ZM4.95072 2.99141L5.02138 3.06217L4.95072 2.99141ZM12.7887 4.25366C13.2263 4.68416 13.5743 5.19703 13.8127 5.76269C14.051 6.32835 14.175 6.93561 14.1775 7.54944C14.18 8.16327 14.061 8.77152 13.8272 9.3391C13.5935 9.90669 13.2497 10.4224 12.8156 10.8564C12.3816 11.2905 11.8659 11.6343 11.2983 11.868C10.7307 12.1018 10.1225 12.2208 9.50865 12.2183C8.89482 12.2158 8.28756 12.0918 7.7219 11.8535C7.15623 11.6151 6.64336 11.2671 6.21287 10.8295C5.35255 9.95509 4.87263 8.77613 4.87762 7.54944C4.88262 6.32275 5.37213 5.14773 6.23954 4.28033C7.10694 3.41292 8.28196 2.92341 9.50865 2.91841C10.7353 2.91342 11.9143 3.39335 12.7887 4.25366Z"
                  fill="black"
                  stroke="black"
                  stroke-width="0.2"
                />
              </svg>
            </span>
          </a>

          <!-- Container with two dropdown menus -->
          <div class="relative" data-te-dropdown1-ref>
            <!-- First dropdown trigger -->
            <a
              class="hidden-arrow mr-4 flex items-center text-secondary-500 transition duration-200 hover:text-secondary-400 hover:ease-in-out focus:text-secondary-400 disabled:text-black/30 motion-reduce:transition-none"
              href="#"
              id="dropdownMenuButton1"
              role="button"
            >
              <!-- Dropdown trigger icon -->
              <span class="[&>svg]:w-5">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="25"
                  height="25"
                  viewBox="0 0 25 25"
                  fill="none"
                >
                  <path
                    d="M14.5834 20.8334C15.1359 20.8334 15.6658 20.6139 16.0566 20.2232C16.4473 19.8325 16.6667 19.3026 16.6667 18.75C16.6667 18.1975 16.4473 17.6676 16.0566 17.2769C15.6658 16.8862 15.1359 16.6667 14.5834 16.6667C14.0309 16.6667 13.501 16.8862 13.1103 17.2769C12.7196 17.6676 12.5001 18.1975 12.5001 18.75C12.5001 19.3026 12.7196 19.8325 13.1103 20.2232C13.501 20.6139 14.0309 20.8334 14.5834 20.8334ZM7.29174 20.8334C7.84428 20.8334 8.37418 20.6139 8.76488 20.2232C9.15558 19.8325 9.37508 19.3026 9.37508 18.75C9.37508 18.1975 9.15558 17.6676 8.76488 17.2769C8.37418 16.8862 7.84428 16.6667 7.29174 16.6667C6.73921 16.6667 6.20931 16.8862 5.81861 17.2769C5.4279 17.6676 5.20841 18.1975 5.20841 18.75C5.20841 19.3026 5.4279 19.8325 5.81861 20.2232C6.20931 20.6139 6.73921 20.8334 7.29174 20.8334ZM20.873 6.16981C21.133 6.16142 21.3796 6.05223 21.5606 5.86531C21.7416 5.6784 21.8428 5.42842 21.8428 5.16825C21.8428 4.90807 21.7416 4.6581 21.5606 4.47118C21.3796 4.28427 21.133 4.17507 20.873 4.16669H19.674C18.7345 4.16669 17.922 4.81877 17.7178 5.73544L16.4126 11.6125C16.2084 12.5292 15.3959 13.1813 14.4563 13.1813H6.63133L5.12924 7.17085H14.8636C15.1212 7.1591 15.3644 7.0485 15.5425 6.86205C15.7206 6.67561 15.82 6.42767 15.82 6.16981C15.82 5.91195 15.7206 5.66401 15.5425 5.47757C15.3644 5.29113 15.1212 5.18052 14.8636 5.16877H5.12924C4.82473 5.16868 4.5242 5.23802 4.25051 5.37151C3.97682 5.50501 3.73716 5.69915 3.54976 5.93917C3.36236 6.17919 3.23215 6.45878 3.16903 6.75668C3.10591 7.05458 3.11154 7.36295 3.1855 7.65835L4.68758 13.6667C4.79586 14.1002 5.046 14.4851 5.39821 14.7601C5.75042 15.0351 6.18447 15.1845 6.63133 15.1844H14.4563C15.368 15.1845 16.2524 14.8737 16.9636 14.3032C17.6748 13.7328 18.1701 12.9369 18.3678 12.0469L19.674 6.16981H20.873Z"
                    fill="black"
                  />
                </svg>
              </span>
              <!-- cart counter -->
              <span
                class="cart-count absolute -mt-4 ml-2.5 rounded-full px-[0.35em] py-[0.15em] text-[0.6rem] font-bold leading-none text-white"
                >1</span
              >
            </a>
          </div>

          <!-- Second dropdown container -->
          <div class="relative" data-te-dropdown-ref>
            <!-- Second dropdown trigger -->
            <a
              class="hidden-arrow flex items-center whitespace-nowrap transition duration-150 ease-in-out motion-reduce:transition-none"
              href="#"
              id="dropdownMenuButton2"
              role="button"
              data-te-dropdown-toggle-ref
              aria-expanded="false"
            >
              <!-- User avatar -->
              <img
                src="https://tecdn.b-cdn.net/img/new/avatars/2.jpg"
                class="rounded-full"
                style="height: 25px; width: 25px"
                alt=""
                loading="lazy"
              />
            </a>
            <!-- Second dropdown menu -->
            <ul
              class="absolute left-auto right-0 z-[1000] float-left m-0 mt-1 hidden min-w-max list-none overflow-hidden rounded-lg border-none bg-white bg-clip-padding text-left text-base shadow-lg dark:bg-neutral-700 [&[data-te-dropdown-show]]:block"
              aria-labelledby="dropdownMenuButton2"
              data-te-dropdown-menu-ref
            >
              <!-- Second dropdown menu items -->
              <li>
                <a
                  class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm font-normal text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-white/30"
                  href="#"
                  data-te-dropdown-item-ref
                  >Action</a
                >
              </li>
              <li>
                <a
                  class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm font-normal text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-white/30"
                  href="#"
                  data-te-dropdown-item-ref
                  >Another action</a
                >
              </li>
              <li>
                <a
                  class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm font-normal text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-white/30"
                  href="#"
                  data-te-dropdown-item-ref
                  >Something else here</a
                >
              </li>
            </ul>
          </div>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
// import { Collapse, Dropdown, initTE } from "tw-elements";

export default {
  data() {
    return {};
  },
  mounted() {
    // initTE({ Collapse, Dropdown });
  },
  name: "headerComponent",
};
</script>

<style lang="scss" scoped>
.black-header {
  height: 44px;
  background: #020202;
}

.heading1 {
  display: flex;
  // width: 184px;
  height: 44px;
  flex-direction: column;
  justify-content: center;
  margin-left: 25px;
  // margin-left: 253px;
  p {
    color: #a2a6b0;
    font-size: 12px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
  }
}

.heading2 {
  color: #acacac;
  text-align: center;
  font-size: 12px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  display: flex;
  height: 44px;
  flex-direction: column;
  justify-content: center;
  margin: auto;
}

li {
  display: flex;
  align-items: center;
  a {
    color: #000;
    text-align: center;
    font-family: Poppins;
    font-size: 14px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
  }
}

.cart-count {
  background: var(--color-3);
  width: 16px;
  height: 16px;
  color: #fff;
  text-align: center;
  font-size: 10px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
}

.our-deals {
  border-radius: 50px;
  border: 2px solid var(--color-3);
  display: inline-flex;
  padding: 8px 26px;
  align-items: center;
  gap: 10px;
  color: var(--color-3);
  text-align: center;
  font-size: 14px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}
</style>
