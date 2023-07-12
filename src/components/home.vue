<template>
<Header />
  <div class="home-container" style="margin-left: 253px">
  <div>
  <img src="../assets/banner.png" alt="" style="height: 104px;"></div>
    <h6
      style="
        color: #000;
        text-align: left;
        font-size: 32px;
        font-style: normal;
        font-weight: 600;
        line-height: normal;
        margin-bottom: 20px
      "
    >
      MSI PS Series (20)
    </h6>
    <div class="flex">
      <!-- Sidebar with filters -->
      <div style="width: 234px">
        <div class="filter-container">
          <h4 class="filter-heading">Filters</h4>
          <button type="button" class="clear-filters" @click="clearFilters()">
            Clear Filter
          </button>
          <div id="filterAccordion">
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
                  data-te-collapse-collapsed
                  data-te-target="#collapseTwo"
                  aria-expanded="false"
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
                class="!visible hidden"
                data-te-collapse-item
                aria-labelledby="headingTwo"
                data-te-parent="#filterAccordion"
              >
                <div class="px-5 py-4">
                  <div v-for="(price, i) in prices" :key="i" class="flex">
                    <p class="category-title">
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
                    <span style="margin-left: auto" class="category-count">(15)</span>
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
                  data-te-collapse-collapsed
                  data-te-target="#collapseThree"
                  aria-expanded="false"
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
                class="!visible hidden"
                data-te-collapse-item
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
                  data-te-collapse-collapsed
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
                class="!visible hidden"
                data-te-collapse-item
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

        <div class="filter-container" style="height: 118.53px;">
          <h4 class="filter-heading">My Wish List</h4>
          <p class="compare-txt">You have no items in your wish list.</p>
        </div>

        <div>
          <img src="../assets/side-img.png" alt="" />
        </div>
      </div>

      <!-- Main content -->
      <div class="w-3/4 p-4">
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
            v-for="(product, i) in filteredProducts"
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
      </div>
    </div>
  </div>
</template>

<script>
import { Collapse, initTE } from "tw-elements";
initTE({ Collapse });

import Header from './header.vue';

export default {
  data() {
    return {
      selectedCategories: [],
      selectedColor: "",
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
      products: [
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 2,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 3,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 2,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 2,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 2,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 3,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 3,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          category: 1,
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
      ],
    };
  },
  name: "HomeComponent",
  components: {
    Header
  },
  computed: {
    filteredProducts() {
      if (this.selectedCategories.length === 0) {
        return this.products;
      } else {
        return this.products.filter((product) => {
          return this.selectedCategories.some(
            (category) => category.id === product.category
          );
        });
      }
    },
  },
  methods: {
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
  border: 2px solid var(--color-5, #a2a6b0);
  color: var(--color-5, #a2a6b0);
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
  color: var(--color-5, #a2a6b0);
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
  border: 1px solid var(--color-6, #cacdd8);
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
  background: var(--color-3, #0156ff);
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
</style>
