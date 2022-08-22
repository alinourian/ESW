<template>
  <div class="product-card">
    <div class="product-tumb">
      <img :src="workshop.img" alt="">
    </div>
    <div class="product-details">
      <p>آخرین مهلت پیش ثبت نام: {{ workshop.expirationData }}</p>
      <div class="product-bottom-details">
        <div class="product-price">
          <h3>
            {{ workshop.price }}
            تومان
          </h3>
        </div>
        <div class="product-links">
          <a :href="workshop.payLink" target="_blank">
<!--            <i class="fa fa-shopping-cart"></i>-->
            <img :src="shopIcon" alt="">
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import shopIcon from '../statics/white-shopping-cart2.png';
export default {
  props: {
    workshop: {}
  },
  data() {
    return {
      shopIcon
    }
  }
}
</script>

<style scoped>

@media (max-width: 600px) {
  .product-card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: max(30vw, 280px);
    min-height: fit-content;
    margin: 15px 30px;
    padding: min(5%,30px) 5% 5% 5%;
    background: transparent;
    border: 1px solid var(--tertiary-color);
  }
}

@media (min-width: 600px) {
  .product-card {
    display: flex;
    flex-direction: column;
    justify-content: center;
    width: max(30vw, 280px);
    min-height: max(560px, 30vw);
    margin: 15px 30px;
    padding: min(5%,30px) 5% 5% 5%;
    background: transparent;
    border: 1px solid var(--tertiary-color);
  }
}

.product-card .product-tumb {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 300px;
  padding: 2%;
  background: #1a1d3c;
}

.product-card .product-tumb > img {
  max-width: 100%;
  max-height: 100%;
}

.product-card .product-details {
  padding: 30px;
}

.product-card .product-details >>> a {
  font-weight: bold;
  display: block;
  text-transform: uppercase;
  color: var(--secondary-color);
  text-decoration: none;
  transition: 0.3s;
}

.product-card .product-details >>> a:hover {
  color: #fbb72c;
}

.product-card .product-details > p {
  font-size: 15px;
  line-height: 22px;
  margin-bottom: 18px;
  color: #999;
}
.product-bottom-details {
  overflow: hidden;
  border-top: 1px solid #eee;
  padding-top: 20px;
  display: flex;
  flex-direction: row-reverse;
  align-self: center;
}


.product-bottom-details > div {
  text-align:center;
  float: right;
  width: 50%;
}

.product-price {
  font-size: 18px;
  color: #ffffff;
  font-weight: 600;
  align-self: center;
}


.product-links {
  text-align: right;
}

.product-links > a {
  display: inline-block;
  margin: 0;
  color: #e1e1e1;
  transition: 0.3s;
  font-size: 17px;
}

.product-links > a:hover {
  color: #fbb72c;
}

.product-links > a > img {
  width: 40px;
  color: white;
  /*filter: brightness(0) saturate(100%) invert(100%) sepia(0%) saturate(0%) hue-rotate(234deg) brightness(103%) contrast(103%);*/
}
</style>