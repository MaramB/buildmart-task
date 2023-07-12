<template>
  <Header />
  <div class="home-container">
    <div>
      <img src="../assets/banner.png" alt="" style="height: 104px" />
    </div>
    <nav class="bg-grey-light w-full rounded-md" style="padding: 19px 0">
      <ol class="list-reset flex">
        <li>
          <a
            href="#"
            class="transition duration-150 ease-in-out hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600"
            >Home</a
          >
        </li>
        <li>
          <span class="mx-2 text-neutral-500 dark:text-neutral-400">></span>
        </li>
        <li>
          <a
            href="#"
            class="transition duration-150 ease-in-out hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600"
            >Laptops</a
          >
        </li>
        <li>
          <span class="mx-2 text-neutral-500 dark:text-neutral-400">></span>
        </li>
        <li>
          <a
            href="#"
            class="transition duration-150 ease-in-out hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600"
            >Everyday Use Notebooks</a
          >
        </li>
        <li>
          <span class="mx-2 text-neutral-500 dark:text-neutral-400">></span>
        </li>
        <li>
          <a
            href="#"
            class="transition duration-150 ease-in-out hover:text-primary-600 focus:text-primary-600 active:text-primary-700 dark:text-primary-400 dark:hover:text-primary-500 dark:focus:text-primary-500 dark:active:text-primary-600"
            >MSI Prestige Series</a
          >
        </li>
        <li>
          <span class="mx-2 text-neutral-500 dark:text-neutral-400">></span>
        </li>
        <li class="text-active text-neutral-500 dark:text-neutral-400">MSI WS Series</li>
      </ol>
    </nav>
    <h6 class="page-title">MSI PS Series (20)</h6>
    <div class="flex">
      <!-- Sidebar with filters -->
      <div style="width: 234px">
        <div class="filter-container">
          <h4 class="filter-heading">Filters</h4>
          <button type="button" class="clear-filters" @click="clearFilters()">
            Clear Filter
          </button>
          <div>
            <!-- Category filter -->
            <div class="rounded-t-lg">
              <h2 class="mb-0 filter-header" id="headingOne">
                <button
                  class="group relative flex w-full items-center rounded-t-[15px] px-5 py-4 text-left text-base text-neutral-800 transition [overflow-anchor:none] hover:z-[2] focus:z-[3] focus:outline-none dark:bg-neutral-800 [&:not([data-te-collapse-collapsed])]:text-primary [&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(229,231,235)] dark:[&:not([data-te-collapse-collapsed])]:bg-neutral-800 dark:[&:not([data-te-collapse-collapsed])]:text-primary-400 dark:[&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(75,85,99)]"
                  style="box-shadow: none"
                  type="button"
                  data-te-collapse-init
                  data-te-target="#collapseOne"
                  aria-expanded="true"
                  aria-controls="collapseOne"
                >
                  Category
                  <span
                    class="ml-auto h-5 w-5 shrink-0 rotate-[-180deg] fill-[#336dec] transition-transform duration-200 ease-in-out group-[[data-te-collapse-collapsed]]:rotate-0 group-[[data-te-collapse-collapsed]]:fill-[#212529] motion-reduce:transition-none dark:fill-blue-300"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="1.5"
                      stroke="currentColor"
                      class="h-6 w-6"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M19.5 8.25l-7.5 7.5-7.5-7.5"
                      />
                    </svg>
                  </span>
                </button>
              </h2>
              <div
                id="collapseOne"
                class="!visible"
                data-te-collapse-item
                data-te-collapse-show
                aria-labelledby="headingOne"
                data-te-parent="#filterAccordion"
              >
                <div class="px-5 py-4">
                  <div v-for="category in categories" :key="category.id" class="flex">
                    <p
                      class="category-title"
                      style="cursor: pointer"
                      @click="addCategory(category)"
                    >
                      {{ category.name }}
                    </p>
                    <span style="margin-left: auto" class="category-count">
                      {{ getProductCount(category.id) }}</span
                    >
                  </div>
                </div>
              </div>
            </div>

            <!-- Price filter -->
            <div class="dark:bg-neutral-800">
              <h2 class="mb-0 filter-header" id="headingTwo">
                <button
                  class="group relative flex w-full items-center rounded-none px-5 py-4 text-left text-base text-neutral-800 transition [overflow-anchor:none] hover:z-[2] focus:z-[3] focus:outline-none [&:not([data-te-collapse-collapsed])]:text-primary [&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(229,231,235)] dark:[&:not([data-te-collapse-collapsed])]:bg-neutral-800 dark:[&:not([data-te-collapse-collapsed])]:text-primary-400 dark:[&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(75,85,99)]"
                  style="box-shadow: none"
                  type="button"
                  data-te-collapse-init
                  data-te-target="#collapseTwo"
                  aria-expanded="true"
                  aria-controls="collapseTwo"
                >
                  Price
                  <span
                    class="-mr-1 ml-auto h-5 w-5 shrink-0 rotate-[-180deg] fill-[#336dec] transition-transform duration-200 ease-in-out group-[[data-te-collapse-collapsed]]:mr-0 group-[[data-te-collapse-collapsed]]:rotate-0 group-[[data-te-collapse-collapsed]]:fill-[#212529] motion-reduce:transition-none dark:fill-blue-300"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="1.5"
                      stroke="currentColor"
                      class="h-6 w-6"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M19.5 8.25l-7.5 7.5-7.5-7.5"
                      />
                    </svg>
                  </span>
                </button>
              </h2>
              <div
                id="collapseTwo"
                class="!visible"
                data-te-collapse-item
                data-te-collapse-show
                aria-labelledby="headingTwo"
                data-te-parent="#filterAccordion"
              >
                <div class="px-5 py-4">
                  <div v-for="(price, i) in prices" :key="i" class="flex">
                    <p
                      class="category-title"
                      :style="{
                        color:
                          selectedPrice && selectedPrice.startRange === price.startRange
                            ? 'var(--color-3)'
                            : '',
                      }"
                      style="cursor: pointer"
                      @click="filterByPrice(price)"
                    >
                      {{
                        price.startRange || price.startRange === 0
                          ? "$" +
                            price.startRange.toLocaleString(undefined, {
                              minimumFractionDigits: 2,
                              maximumFractionDigits: 2,
                            })
                          : ""
                      }}
                      {{
                        price.endRange
                          ? " - $" +
                            price.endRange.toLocaleString(undefined, {
                              minimumFractionDigits: 2,
                              maximumFractionDigits: 2,
                            })
                          : " And Above"
                      }}
                    </p>
                    <span style="margin-left: auto" class="category-count">{{
                      getPriceCount(price)
                    }}</span>
                  </div>
                </div>
              </div>
            </div>

            <!-- Color filter -->
            <div class="dark:bg-neutral-800">
              <h2 class="mb-0 filter-header" id="headingFour">
                <button
                  class="group relative flex w-full items-center rounded-none px-5 py-4 text-left text-base text-neutral-800 transition [overflow-anchor:none] hover:z-[2] focus:z-[3] focus:outline-none [&:not([data-te-collapse-collapsed])]:text-primary [&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(229,231,235)] dark:[&:not([data-te-collapse-collapsed])]:bg-neutral-800 dark:[&:not([data-te-collapse-collapsed])]:text-primary-400 dark:[&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(75,85,99)]"
                  style="box-shadow: none"
                  type="button"
                  data-te-collapse-init
                  data-te-target="#collapseThree"
                  aria-expanded="true"
                  aria-controls="collapseThree"
                >
                  Color
                  <span
                    class="-mr-1 ml-auto h-5 w-5 shrink-0 rotate-[-180deg] fill-[#336dec] transition-transform duration-200 ease-in-out group-[[data-te-collapse-collapsed]]:mr-0 group-[[data-te-collapse-collapsed]]:rotate-0 group-[[data-te-collapse-collapsed]]:fill-[#212529] motion-reduce:transition-none dark:fill-blue-300"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="1.5"
                      stroke="currentColor"
                      class="h-6 w-6"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M19.5 8.25l-7.5 7.5-7.5-7.5"
                      />
                    </svg>
                  </span>
                </button>
              </h2>
              <div
                id="collapseThree"
                class="!visible"
                data-te-collapse-item
                data-te-collapse-show
                aria-labelledby="headingThree"
                data-te-parent="#filterAccordion"
              >
                <div class="px-5 py-4">
                  <div class="flex">
                    <div
                      style="border-radius: 20px; margin-right: 3px"
                      :class="{ 'active-node': selectedColor === 'black' }"
                    >
                      <div
                        class="color-item"
                        @click="selectedColor = 'black'"
                        style="background: #000"
                      ></div>
                    </div>
                    <div
                      style="border-radius: 20px; margin-left: 3px"
                      :class="{ 'active-node': selectedColor === 'red' }"
                    >
                      <div
                        class="color-item"
                        @click="selectedColor = 'red'"
                        style="background: #db0000"
                      ></div>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Filter name -->
            <div class="dark:bg-neutral-800">
              <h2 class="mb-0 filter-header" id="headingFour">
                <button
                  class="group relative flex w-full items-center rounded-none px-5 py-4 text-left text-base text-neutral-800 transition [overflow-anchor:none] hover:z-[2] focus:z-[3] focus:outline-none [&:not([data-te-collapse-collapsed])]:text-primary [&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(229,231,235)] dark:[&:not([data-te-collapse-collapsed])]:bg-neutral-800 dark:[&:not([data-te-collapse-collapsed])]:text-primary-400 dark:[&:not([data-te-collapse-collapsed])]:[box-shadow:inset_0_-1px_0_rgba(75,85,99)]"
                  style="box-shadow: none"
                  type="button"
                  data-te-collapse-init
                  data-te-target="#collapseFour"
                  aria-expanded="false"
                  aria-controls="collapseFour"
                >
                  Filter Name
                  <span
                    class="-mr-1 ml-auto h-5 w-5 shrink-0 rotate-[-180deg] fill-[#336dec] transition-transform duration-200 ease-in-out group-[[data-te-collapse-collapsed]]:mr-0 group-[[data-te-collapse-collapsed]]:rotate-0 group-[[data-te-collapse-collapsed]]:fill-[#212529] motion-reduce:transition-none dark:fill-blue-300"
                  >
                    <svg
                      xmlns="http://www.w3.org/2000/svg"
                      fill="none"
                      viewBox="0 0 24 24"
                      stroke-width="1.5"
                      stroke="currentColor"
                      class="h-6 w-6"
                    >
                      <path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        d="M19.5 8.25l-7.5 7.5-7.5-7.5"
                      />
                    </svg>
                  </span>
                </button>
              </h2>
              <div
                id="collapseFour"
                class="!visible"
                data-te-collapse-item
                data-te-collapse-show
                aria-labelledby="headingFour"
                data-te-parent="#filterAccordion"
              >
                <div class="">
                  <button type="button" class="apply-filter-btn">
                    Apply Filters (2)
                  </button>
                </div>
              </div>
            </div>
          </div>
        </div>

        <div class="filter-container">
          <h4 class="filter-heading">Brands</h4>
          <button type="button" class="clear-filters">All Brands</button>
        </div>

        <div class="flex flex-wrap">
          <div class="w-1/2 logo">
            <div class="logo-img"></div>
          </div>

          <div class="w-1/2 logo">
            <div class="logo-img"></div>
          </div>

          <div class="w-1/2 logo">
            <div class="logo-img"></div>
          </div>

          <div class="w-1/2 logo">
            <div class="logo-img"></div>
          </div>

          <div class="w-1/2 logo">
            <div class="logo-img"></div>
          </div>

          <div class="w-1/2 logo">
            <div class="logo-img"></div>
          </div>
        </div>

        <div class="filter-container">
          <h4 class="filter-heading">Compare Products</h4>
          <p class="compare-txt">You have no items to compare.</p>
        </div>

        <div class="filter-container" style="height: 118.53px">
          <h4 class="filter-heading">My Wish List</h4>
          <p class="compare-txt">You have no items in your wish list.</p>
        </div>

        <div>
          <img src="../assets/side-img.png" alt="" />
        </div>
      </div>

      <!-- Main content -->
      <div class="w-3/4 p-4">
        <div class="position-container flex">
          <p class="position-text">
            Items {{ (currentPage - 1) * pageSize + 1 }}-{{
              Math.min(currentPage * pageSize, filteredProducts.length)
            }}
            of {{ filteredProducts.length }}
          </p>
          <div class="flex" style="margin-left: auto; margin-bottom: 10px">
            <!-- SORT BY DROPDOWN -->
            <div class="relative" data-te-dropdown-ref>
              <button
                class="flex items-center whitespace-nowrap position-btn"
                type="button"
                id="dropdownMenuButton1h"
                data-te-dropdown-toggle-ref
                aria-expanded="false"
                data-te-ripple-init
                data-te-ripple-color="light"
              >
                <span class="filter-span">Sort By:{{ "&nbsp;" }}</span> {{ sortBy }}
                <span class="ml-2 w-2">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                    class="h-5 w-5"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
                      clip-rule="evenodd"
                    />
                  </svg>
                </span>
              </button>
              <ul
                style="width: 100%"
                class="absolute z-[1000] float-left m-0 hidden min-w-max list-none overflow-hidden rounded-lg border-none bg-white bg-clip-padding text-left text-base shadow-lg dark:bg-neutral-700 [&[data-te-dropdown-show]]:block"
                aria-labelledby="dropdownMenuButton1h"
                data-te-dropdown-menu-ref
              >
                <li>
                  <a
                    :class="{
                      'font-semibold': sortBy === 'Position',
                      'font-normal': sortBy !== 'Position',
                    }"
                    class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-neutral-600"
                    @click.prevent
                    @click="sortBy = 'Position'"
                    data-te-dropdown-item-ref
                    >Position</a
                  >
                </li>
                <li>
                  <a
                    :class="{
                      'font-semibold': sortBy === 'Price',
                      'font-normal': sortBy !== 'Price',
                    }"
                    class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-neutral-600"
                    @click.prevent
                    @click="sortBy = 'Price'"
                    data-te-dropdown-item-ref
                    >Price</a
                  >
                </li>
              </ul>
            </div>

            <!-- PAGES PER PAGE DROPDOWN -->
            <div class="relative" data-te-dropdown-ref>
              <button
                class="flex items-center whitespace-nowrap position-btn"
                type="button"
                id="dropdownMenuButton2h"
                data-te-dropdown-toggle-ref
                aria-expanded="false"
                data-te-ripple-init
                data-te-ripple-color="light"
              >
                <span class="filter-span">Show:{{ "&nbsp;" }}</span> {{ pageSize }} Per
                Page
                <span class="ml-2 w-2">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    viewBox="0 0 20 20"
                    fill="currentColor"
                    class="h-5 w-5"
                  >
                    <path
                      fill-rule="evenodd"
                      d="M5.23 7.21a.75.75 0 011.06.02L10 11.168l3.71-3.938a.75.75 0 111.08 1.04l-4.25 4.5a.75.75 0 01-1.08 0l-4.25-4.5a.75.75 0 01.02-1.06z"
                      clip-rule="evenodd"
                    />
                  </svg>
                </span>
              </button>
              <ul
                style="width: 100%"
                class="absolute z-[1000] float-left m-0 hidden min-w-max list-none overflow-hidden rounded-lg border-none bg-white bg-clip-padding text-left text-base shadow-lg dark:bg-neutral-700 [&[data-te-dropdown-show]]:block"
                aria-labelledby="dropdownMenuButton2h"
                data-te-dropdown-menu-ref
              >
                <li>
                  <a
                    :class="{
                      'font-semibold': pageSize === 5,
                      'font-normal': pageSize !== 5,
                    }"
                    class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-neutral-600"
                    @click.prevent
                    @click="pageSize = 5"
                    data-te-dropdown-item-ref
                    >5</a
                  >
                </li>
                <li>
                  <a
                    :class="{
                      'font-semibold': pageSize === 10,
                      'font-normal': pageSize !== 10,
                    }"
                    class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-neutral-600"
                    @click.prevent
                    @click="pageSize = 10"
                    data-te-dropdown-item-ref
                    >10</a
                  >
                </li>
                <li>
                  <a
                    :class="{
                      'font-semibold': pageSize === 35,
                      'font-normal': pageSize !== 35,
                    }"
                    class="block w-full whitespace-nowrap bg-transparent px-4 py-2 text-sm text-neutral-700 hover:bg-neutral-100 active:text-neutral-800 active:no-underline disabled:pointer-events-none disabled:bg-transparent disabled:text-neutral-400 dark:text-neutral-200 dark:hover:bg-neutral-600"
                    @click.prevent
                    @click="pageSize = 35"
                    data-te-dropdown-item-ref
                    >35</a
                  >
                </li>
              </ul>
            </div>

            <!-- Grid/List View Toggles -->
            <div class="flex view-toggle">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="32"
                height="32"
                viewBox="0 0 32 32"
                fill="none"
              >
                <rect width="32" height="32" fill="white" />
                <rect
                  x="6.90039"
                  y="6.90002"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="6.90039"
                  y="14.2143"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="6.90039"
                  y="21.5286"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="14.2139"
                  y="14.2143"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="14.2139"
                  y="21.5286"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="14.2139"
                  y="6.90002"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="21.5283"
                  y="14.2143"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="21.5283"
                  y="21.5286"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
                <rect
                  x="21.5283"
                  y="6.90002"
                  width="3.57143"
                  height="3.57143"
                  fill="black"
                  stroke="black"
                />
              </svg>

              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="32"
                height="32"
                viewBox="0 0 32 32"
                fill="none"
              >
                <rect width="32" height="32" fill="white" />
                <rect
                  x="4.57129"
                  y="21.0286"
                  width="9.14286"
                  height="2.74286"
                  fill="#A2A6B0"
                />
                <rect
                  x="4.57129"
                  y="8.22858"
                  width="21.9429"
                  height="2.74286"
                  fill="#A2A6B0"
                />
                <rect
                  x="4.57129"
                  y="14.6286"
                  width="16.4571"
                  height="2.74286"
                  fill="#A2A6B0"
                />
              </svg>
            </div>
          </div>
        </div>

        <!-- filters result -->
        <div class="flex flex-wrap">
          <div
            v-for="category in selectedCategories"
            :key="category.id"
            class="filter-result"
          >
            <div class="filter-result-container" style="padding: 0 10px">
              <p class="filter">
                {{ category.name }}
                <span class="review-text"> ({{ getProductCount(category.id) }}) </span>
              </p>
              <div
                style="cursor: pointer; margin-left: 5px"
                @click="removeCategory(category)"
              >
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="20"
                  height="20"
                  viewBox="0 0 20 20"
                  fill="none"
                >
                  <circle cx="10" cy="10" r="10" fill="#C94D3F" />
                  <path d="M7 7L13.5 13.5" stroke="white" stroke-linecap="round" />
                  <path d="M13.5 7L7 13.5" stroke="white" stroke-linecap="round" />
                </svg>
              </div>
            </div>
          </div>

          <div
            class="filter-result"
            style="width: 91.015px"
            v-if="selectedCategories.length > 0"
          >
            <div
              class="filter-result-container"
              style="width: 91.015px; cursor: pointer"
              @click="clearAll()"
            >
              <p class="filter">Clear All</p>
            </div>
          </div>
        </div>

        <!-- Product listing -->
        <div class="flex flex-wrap">
          <div
            style="width: 200px"
            class="product-card"
            v-for="(product, i) in paginatedFilteredProducts"
            :key="i"
          >
            <div class="stock">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="11"
                height="10"
                viewBox="0 0 11 10"
                fill="none"
              >
                <circle cx="5.5" cy="5" r="5" fill="#78A962" />
                <path
                  d="M7.5 4L4.98404 7L3.5 5.27853"
                  stroke="white"
                  stroke-linecap="round"
                />
              </svg>
              <span class="stock-title">{{
                product.availability ? "in stock" : "out of stock"
              }}</span>
            </div>
            <img class="product-img" src="../assets/image0.png" alt="Product Image" />
            <div class="p-4">
              <div class="flex items-center">
                <div class="flex items-center">
                  <!-- Rating Stars -->
                  <div class="flex">
                    <svg
                      v-for="star in Math.floor(product.rating)"
                      :key="star"
                      xmlns="http://www.w3.org/2000/svg"
                      width="14"
                      height="13"
                      viewBox="0 0 14 13"
                      fill="#E9A426"
                    >
                      <path
                        d="M6.75474 0.173835C6.7919 0.10127 6.8956 0.10127 6.93276 0.173834L8.77297 3.76772C8.7875 3.79609 8.81467 3.81583 8.84614 3.82088L12.8328 4.46045C12.9133 4.47337 12.9453 4.572 12.8878 4.62976L10.0385 7.49048C10.016 7.51306 10.0056 7.54501 10.0105 7.57649L10.6342 11.5657C10.6468 11.6462 10.5629 11.7072 10.4902 11.6703L6.88897 9.84443C6.86055 9.83002 6.82695 9.83002 6.79853 9.84443L3.19733 11.6703C3.12462 11.7072 3.04072 11.6462 3.05331 11.5657L3.67698 7.57649C3.68191 7.54501 3.67153 7.51306 3.64904 7.49048L0.799704 4.62976C0.742173 4.572 0.77422 4.47337 0.854715 4.46045L4.84136 3.82088C4.87283 3.81583 4.9 3.79609 4.91453 3.76772L6.75474 0.173835Z"
                      />
                    </svg>
                    <svg
                      v-for="star in 5 - Math.floor(product.rating)"
                      :key="star"
                      xmlns="http://www.w3.org/2000/svg"
                      width="14"
                      height="13"
                      viewBox="0 0 14 13"
                      fill="#CACDD8"
                    >
                      <path
                        d="M6.91099 0.173835C6.94815 0.10127 7.05185 0.10127 7.08901 0.173834L8.92922 3.76772C8.94375 3.79609 8.97092 3.81583 9.00239 3.82088L12.989 4.46045C13.0695 4.47337 13.1016 4.572 13.044 4.62976L10.1947 7.49048C10.1722 7.51306 10.1618 7.54501 10.1668 7.57649L10.7904 11.5657C10.803 11.6462 10.7191 11.7072 10.6464 11.6703L7.04522 9.84443C7.0168 9.83002 6.9832 9.83002 6.95478 9.84443L3.35358 11.6703C3.28087 11.7072 3.19697 11.6462 3.20956 11.5657L3.83323 7.57649C3.83816 7.54501 3.82778 7.51306 3.80529 7.49048L0.955954 4.62976C0.898423 4.572 0.93047 4.47337 1.01096 4.46045L4.99761 3.82088C5.02908 3.81583 5.05625 3.79609 5.07078 3.76772L6.91099 0.173835Z"
                      />
                    </svg>
                  </div>
                  <!-- Reviews Count -->
                  <p class="ml-2 review-text">Reviews ({{ product.reviews }})</p>
                </div>
              </div>
              <!-- Product Title -->
              <h3 class="mt-2 product-title">EX DISPLAY: {{ product.title }}</h3>
              <!-- Price -->
              <div class="price-container">
                <p class="mt-1 old-price">${{ product.oldPrice }}</p>
                <p class="mt-1 new-price">${{ product.newPrice }}</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Pagination -->
        <nav aria-label="Page navigation example" class="pagination-container">
          <ul class="list-style-none flex">
            <li>
              <a
                class="relative block rounded-full bg-transparent px-3 py-1.5 text-sm text-neutral-500 transition-all duration-300 dark:text-neutral-400"
                @click="previousPage"
                :class="{ 'pointer-events-none': currentPage === 1 }"
                >{{ "<" }}</a
              >
            </li>
            <template v-for="pageNumber in totalPageCount" :key="pageNumber">
              <li
                :class="{
                  active: pageNumber === currentPage,
                }"
              >
                <a
                  class="relative block rounded-full bg-transparent px-3 py-1.5 text-sm transition-all duration-300"
                  :class="[
                    'text-neutral-600',
                    {
                      active: pageNumber === currentPage,
                      'text-neutral-600 hover:bg-neutral-100 dark:text-white dark:hover:bg-neutral-700 dark:hover:text-white':
                        pageNumber !== currentPage,
                    },
                  ]"
                  @click="goToPage(pageNumber)"
                  href="#!"
                  >{{ pageNumber }}</a
                >
              </li>
            </template>
            <li>
              <a
                class="relative block rounded-full bg-transparent px-3 py-1.5 text-sm text-neutral-500 transition-all duration-300 dark:text-neutral-400"
                @click="nextPage"
                :class="{ 'pointer-events-none': currentPage === totalPageCount }"
                >{{ ">" }}</a
              >
            </li>
          </ul>
        </nav>
      </div>
    </div>

    <div class="info flex">
      <div class="info-container">
        <div class="info-icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="65"
            height="65"
            viewBox="0 0 65 65"
            fill="none"
          >
            <circle cx="32.5" cy="32.5" r="32.5" fill="#0156FF" />
            <svg
              xmlns="http://www.w3.org/2000/svg"
              width="30"
              height="31"
              viewBox="0 0 30 31"
              fill="none"
              x="17.5"
              y="17"
            >
              <path
                d="M14.9121 3.39246C8.10683 3.39246 2.57031 8.92898 2.57031 15.7342V20.8474C2.57031 22.1112 3.67737 23.1393 5.03867 23.1393H6.27284C6.60017 23.1393 6.91409 23.0093 7.14554 22.7778C7.37699 22.5464 7.50702 22.2324 7.50702 21.9051V15.5577C7.50702 15.2304 7.37699 14.9165 7.14554 14.685C6.91409 14.4536 6.60017 14.3236 6.27284 14.3236H5.15221C5.83841 9.5473 9.94823 5.86081 14.9121 5.86081C19.8759 5.86081 23.9858 9.5473 24.672 14.3236H23.5513C23.224 14.3236 22.9101 14.4536 22.6786 14.685C22.4472 14.9165 22.3172 15.2304 22.3172 15.5577V23.1393C22.3172 24.5006 21.2101 25.6076 19.8488 25.6076H17.3804V24.3735H12.4437V28.076H19.8488C22.5714 28.076 24.7855 25.8619 24.7855 23.1393C26.1468 23.1393 27.2539 22.1112 27.2539 20.8474V15.7342C27.2539 8.92898 21.7173 3.39246 14.9121 3.39246Z"
                fill="white"
              />
            </svg>
          </svg>
        </div>

        <p class="info-title">Product Support</p>

        <p class="info-description">
          Up to 3 years on-site warranty available for your peace of mind.
        </p>
      </div>

      <div class="info-container">
        <div class="info-icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="65"
            height="65"
            viewBox="0 0 65 65"
            fill="none"
          >
            <g>
              <circle cx="32.5" cy="32.5" r="32.5" fill="#0156FF" />
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="30"
                height="30"
                viewBox="0 0 30 30"
                fill="none"
                x="17.5"
                y="17.5"
              >
                <path
                  d="M17.82 27.18L15 30L12.18 27.18C6.6375 25.9 2.5 20.93 2.5 15C2.5 8.1 8.1 2.5 15 2.5C21.9 2.5 27.5 8.1 27.5 15C27.5 20.93 23.3625 25.9 17.82 27.18ZM7.52875 19.27C9.36375 22.0075 12.1187 23.75 15.2 23.75C18.28 23.75 21.0362 22.0088 22.87 19.27C20.7897 17.3257 18.0474 16.246 15.2 16.25C12.3521 16.2457 9.60939 17.3255 7.52875 19.27ZM15 13.75C15.9946 13.75 16.9484 13.3549 17.6517 12.6517C18.3549 11.9484 18.75 10.9946 18.75 10C18.75 9.00544 18.3549 8.05161 17.6517 7.34835C16.9484 6.64509 15.9946 6.25 15 6.25C14.0054 6.25 13.0516 6.64509 12.3483 7.34835C11.6451 8.05161 11.25 9.00544 11.25 10C11.25 10.9946 11.6451 11.9484 12.3483 12.6517C13.0516 13.3549 14.0054 13.75 15 13.75Z"
                  fill="white"
                />
              </svg>
            </g>
          </svg>
        </div>

        <p class="info-title">Personal Account</p>

        <p class="info-description">
          With big discounts, free delivery and a dedicated support specialist.
        </p>
      </div>

      <div class="info-container">
        <div class="info-icon">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            width="65"
            height="65"
            viewBox="0 0 65 65"
            fill="none"
          >
            <circle cx="32.5" cy="32.5" r="32.5" fill="#0156FF" />
            <foreignObject width="26" height="26" x="19.8" y="19.8">
              <svg
                xmlns="http://www.w3.org/2000/svg"
                width="26"
                height="26"
                viewBox="0 0 26 26"
                fill="none"
              >
                <g clip-path="url(#clip0_1513_1494)">
                  <path
                    d="M25.2047 0.526524C25.1293 0.33869 24.9844 0.187163 24.8001 0.103468C24.6158 0.019772 24.4063 0.0103515 24.2152 0.0771657C24.0242 0.14398 23.8662 0.281885 23.7742 0.462191C23.6823 0.642497 23.6633 0.851322 23.7214 1.04522C24.9291 4.51622 22.5319 7.10842 20.7041 8.49682L19.9657 7.43862C19.7174 7.08372 19.1623 6.78862 18.7307 6.78342L14.5863 6.80162C14.08 6.81691 13.5873 6.96873 13.1602 7.24102L0.948006 15.8041C0.663949 16.004 0.470671 16.3083 0.410489 16.6504C0.350307 16.9925 0.428126 17.3445 0.626906 17.6293L6.17661 25.5697C6.59261 26.1612 7.25691 26.0897 7.84971 25.6763L20.0619 17.1119C20.4129 16.8636 20.8185 16.328 20.9615 15.9185L22.2589 11.83C22.4019 11.4218 22.3148 10.7991 22.0665 10.4442L21.6167 9.79942C24.0711 7.91832 26.6191 4.59422 25.2047 0.526524ZM19.5224 12.6919C19.2974 12.8494 19.0436 12.961 18.7755 13.0204C18.5074 13.0797 18.2302 13.0857 17.9597 13.0379C17.6893 12.9901 17.431 12.8894 17.1994 12.7418C16.9679 12.5941 16.7678 12.4022 16.6104 12.1771C16.2918 11.7217 16.1669 11.1584 16.2632 10.611C16.3595 10.0636 16.669 9.57674 17.1239 9.25732C17.4805 9.00748 17.9063 8.87531 18.3416 8.87927C18.777 8.88323 19.2003 9.02314 19.5523 9.27942C19.1987 9.49262 18.9556 9.61742 18.9101 9.63692C18.749 9.71376 18.6187 9.84305 18.5406 10.0036C18.4626 10.1642 18.4414 10.3465 18.4805 10.5207C18.5196 10.6949 18.6168 10.8506 18.756 10.9624C18.8952 11.0741 19.0683 11.1353 19.2468 11.1358C19.3586 11.1358 19.473 11.1098 19.5809 11.0591C19.8331 10.9395 20.1035 10.7978 20.3856 10.6301C20.4505 11.0202 20.4039 11.4207 20.2512 11.7854C20.0985 12.1502 19.8459 12.4644 19.5224 12.6919Z"
                    fill="white"
                  />
                </g>
                <defs>
                  <clipPath id="clip0_1513_1494">
                    <rect width="26" height="26" fill="white" />
                  </clipPath>
                </defs>
              </svg>
            </foreignObject>
          </svg>
        </div>

        <p class="info-title">Amazing Savings</p>

        <p class="info-description">
          Up to 70% off new Products, you can be sure of the best price.
        </p>
      </div>
    </div>
  </div>
  <Footer />
</template>

<script>
import { Collapse, Dropdown, Ripple, initTE } from "tw-elements";

import productsData from "@/products.json";

import Header from "./header.vue";
import Footer from "./footer.vue";

export default {
  data() {
    return {
      sortBy: "Position",
      selectedCategories: [],
      selectedColor: "",
      selectedPrice: null,
      categories: [
        {
          id: 1,
          name: "CUSTOM PCS",
        },
        {
          id: 2,
          name: "MSI ALL-IN-ONE PCS",
        },
        { id: 3, name: "HP/COMPAQ PCS" },
      ],
      prices: [
        {
          startRange: 0,
          endRange: 1000,
        },
        {
          startRange: 1000,
          endRange: 2000,
        },
        {
          startRange: 2000,
          endRange: 3000,
        },
        {
          startRange: 3000,
          endRange: 4000,
        },
        {
          startRange: 4000,
          endRange: 5000,
        },
        {
          startRange: 5000,
          endRange: 6000,
        },
        {
          startRange: 6000,
          endRange: 7000,
        },
        {
          startRange: 7000,
        },
      ],
      products: productsData,
      pageSize: 10, // number of products per page
      currentPage: 1, // initial current page
    };
  },
  name: "HomeComponent",
  components: {
    Header,
    Footer
  },
  mounted() {
    initTE({ Collapse, Dropdown, Ripple });
  },
  computed: {
    paginatedFilteredProducts() {
      // Calculate start and end indexes for the current page
      const startIndex = (this.currentPage - 1) * this.pageSize;
      const endIndex = startIndex + this.pageSize;

      // Return a subset of products based on the current page and page size
      return this.filteredProducts.slice(startIndex, endIndex);
    },
    filteredProducts() {
      if (this.selectedCategories.length === 0 && !this.selectedPrice) {
        // If no categories or price range are selected, return all products
        return this.products;
      } else {
        // Apply filtering based on selected categories and price range
        return this.products.filter((product) => {
          const matchCategory =
            this.selectedCategories.length === 0 ||
            this.selectedCategories.some((category) => category.id === product.category);

          const matchPrice =
            !this.selectedPrice ||
            ((this.selectedPrice.startRange || this.selectedPrice.startRange === 0) &&
              product.newPrice >= this.selectedPrice.startRange &&
              (!this.selectedPrice.endRange ||
                product.newPrice < this.selectedPrice.endRange));

          // Return true if the product matches the selected categories and price range
          return matchCategory && matchPrice;
        });
      }
    },
    totalPageCount() {
      // Calculate the total number of pages based on the products array and page size
      return Math.ceil(this.filteredProducts.length / this.pageSize);
    },
  },
  methods: {
    getPriceCount(price) {
      const count = this.products.filter((product) => {
        if (price.startRange || price.startRange === 0) {
          if (product.newPrice >= price.startRange) {
            if (price.endRange) {
              return product.newPrice < price.endRange;
            }
            return true;
          }
        } else if (price.endRange) {
          return product.newPrice < price.endRange;
        }
        return false;
      }).length;

      return count;
    },
    filterByPrice(price) {
      this.selectedPrice = price;
    },
    getProductCount(categoryId) {
      const productsArr = this.products.filter((item) => item.category === categoryId);
      return productsArr.length;
    },
    isSelectedCategory(category) {
      return this.selectedCategories.some(
        (selectedCategory) => selectedCategory.id === category.id
      );
    },
    addCategory(category) {
      if (!this.isSelectedCategory(category)) {
        this.selectedCategories.push(category);
      }
    },
    removeCategory(category) {
      const index = this.selectedCategories.findIndex(
        (selectedCategory) => selectedCategory.id === category.id
      );
      if (index !== -1) {
        this.selectedCategories.splice(index, 1);
      }
    },
    clearAll() {
      this.selectedCategories = [];
    },
    clearFilters() {
      this.clearAll();
      this.selectedPrice = null;
    },
    goToPage(pageNumber) {
      // Update the current page when a page number is clicked
      this.currentPage = pageNumber;
    },
    previousPage() {
      // Go to the previous page
      if (this.currentPage > 1) {
        this.currentPage--;
      }
    },
    nextPage() {
      // Go to the next page
      if (this.currentPage < this.totalPageCount) {
        this.currentPage++;
      }
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="css" scoped>
.hidden {
  display: none;
}

.filter-container {
  background: #f5f7ff;
  margin-bottom: 10px;
}

.filter-heading {
  color: #000;
  text-align: center;
  font-family: Poppins;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: normal;
  padding: 20px;
}

.filter-header {
  color: #000;
  font-size: 14px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}

.clear-filters {
  display: inline-flex;
  padding: 8px 62px 8px 61px;
  justify-content: center;
  align-items: center;
  border-radius: 50px;
  border: 2px solid var(--color-5);
  color: var(--color-5);
  text-align: center;
  font-family: Poppins;
  font-size: 14px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  margin-bottom: 17px;
}

.category-title {
  color: #000;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: 210%;
}

.category-count {
  color: #000;
  text-align: right;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: 210%;
}

.product-card {
  display: flex;
  padding: 0px 25px;
  flex-direction: column;
  align-items: flex-start;
}

.product-img {
  margin: auto;
}

.review-text {
  color: var(--color-5);
  text-align: center;
  font-size: 12px;
  font-style: normal;
  font-weight: 400;
  line-height: 210%;
}

.product-title {
  color: #000;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: normal;
  width: 185px;
  height: 65px;
  text-align: justify;
}

.stars {
  width: 13px;
  height: 13px;
}

.stock {
  display: flex;
  width: 71px;
  height: 26px;
  padding: 7px 5px 7px 8px;
  justify-content: center;
  align-items: center;
}

.stock-title {
  color: #78a962;
  text-align: center;
  font-size: 10px;
  font-style: normal;
  font-weight: 400;
  line-height: 210%;
  display: flex;
  width: 46px;
  height: 12px;
  flex-direction: column;
  justify-content: center;
  flex-shrink: 0;
}

.price-container {
  display: flex;
  width: 184.159px;
  flex-direction: column;
  justify-content: center;
}
.old-price {
  color: #666;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 140%;
  text-decoration-line: line-through;
  display: flex;
}

.new-price {
  display: flex;
  font-size: 20px;
  font-style: normal;
  font-weight: 600;
  line-height: 140%;
}

.filter-result {
  margin-bottom: 5px;
  margin-right: 5px;
  border-radius: 2px;
  border: 1px solid var(--color-6);
  background: #fff;
  width: auto;
  height: 38px;
  flex-shrink: 0;
}
.filter-result-container {
  display: flex;
  height: 38px;
  justify-content: center;
  align-items: center;
}
.filter {
  color: #000;
  font-size: 13px;
  font-style: normal;
  font-weight: 600;
  line-height: 210%;
}

.active-node {
  outline: 2px solid #0156ff;
}

.color-item {
  border-radius: 20px;
  width: 23px;
  height: 23px;
  margin: 3px;
  cursor: pointer;
}

.apply-filter-btn {
  display: inline-flex;
  padding: 8px 42px 8px 45px;
  justify-content: center;
  align-items: center;
  border-radius: 50px;
  background: var(--color-3);
  color: #fff;
  text-align: center;
  font-family: Poppins;
  font-size: 14px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}

.logo-img {
  width: 88.325px;
  height: 45.97px;
  background-image: url("../assets/logo0.png");
}

.logo {
  display: flex;
  width: 115px;
  padding: 15px 55px;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.compare-txt {
  color: #000;
  text-align: center;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: 130%;
  display: flex;
  height: 47px;
  justify-content: center;
  flex-shrink: 0;
  width: 203.163px;
  margin: auto;
}

.pagination-container {
  display: flex;
  justify-content: center;
}

.pagination-container .li a {
  color: var(--color-5);
  text-align: center;
  font-family: Poppins;
  font-size: 13px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
}

.pagination-container li {
  border: 2px solid var(--color-5);
  border-radius: 50px;
  display: inline-flex;
  padding: 8px 16px;
  align-items: center;
  gap: 10px;
  margin-right: 10px;
}

.active {
  background: var(--color-1);
  border: none !important;
  color: var(--color-7) !important;
}

.home-container {
  width: 95%;
  margin: auto;
}

.page-title {
  color: #000;
  text-align: left;
  font-size: 32px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
  margin-bottom: 20px;
}

.position-text {
  display: flex;
  flex-direction: column;
  justify-content: center;
  color: var(--color-5);
  font-family: Poppins;
  font-size: 13px;
  font-style: normal;
  font-weight: 400;
  line-height: 210%;
}

.position-btn {
  border-radius: 2px;
  border: 2px solid var(--color-6);
  width: 176px;
  height: 50px;
  flex-shrink: 0;
  color: black;
  display: flex;
  justify-content: center;
  font-family: Poppins;
  margin-right: 15px;
  color: #000;
  text-align: center;
  font-family: Poppins;
  font-size: 13px;
  font-style: normal;
  font-weight: 600;
  line-height: 210%;
}
.filter-span {
  color: #a2a6b0;
}

.view-toggle {
  align-items: center;
  gap: 5px;
}

.info {
  background: var(--color-1);
  height: 273px;
  justify-content: center;
  gap: 100px;
}

.info-container {
  display: flex;
  width: 265px;
  flex-direction: column;
  justify-content: center;
  gap: 24px;
}

.info-icon {
  align-items: center;
  display: flex;
  flex-direction: column;
}

.info-title {
  color: #000;
  text-align: center;
  font-family: Poppins;
  font-size: 18px;
  font-style: normal;
  font-weight: 700;
  line-height: 132.5%;
}

.info-description {
  color: #000;
  text-align: center;
  font-family: Poppins;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 140%;
}
</style>
