<template>
  <div class="flex">
    <!-- Sidebar with filters -->
    <div class="w-1/4 p-4">
      <div class="filter-container"></div>
    </div>

    <!-- Main content -->
    <div class="w-3/4 p-4 flex flex-wrap">
      <!-- Product listing -->
      <div class="product-card" v-for="(product, i) in products" :key="i">
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
</template>

<script>
import { Collapse, initTE } from "tw-elements";
initTE({ Collapse });

export default {
  data() {
    return {
      categories: ["CUSTOM PCS", "MSI ALL-IN-ONE PCS", "HP/COMPAQ PCS"],
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
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 3,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
        {
          title: "MSI Pro 16 Flex-036AU 15.6 MULTITOUCH All-In-On lorem",
          oldPrice: 499,
          newPrice: 499,
          availability: 1,
          reviews: 4,
          rating: 4,
        },
      ],
    };
  },
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {},
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="css" scoped>
.hidden {
  display: none;
}

.filter-container {
  background: #f5f7ff;
}

.filter-header {
  color: #000;
  font-size: 14px;
  font-style: normal;
  font-weight: 600;
  line-height: normal;
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
  /* font-family: Poppins; */
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 140%;
  text-decoration-line: line-through;
  display: flex;
}

.new-price {
  display: flex;
  /* font-family: Poppins; */
  font-size: 20px;
  font-style: normal;
  font-weight: 600;
  line-height: 140%;
}
</style>
