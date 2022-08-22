<template>
  <div class="body">
    <div class="header">
      <ul class="navigation">
        <a href="https://ee.sharif.edu/~resana/ESW.html">
          <p>صفحه اصلی</p>
        </a>
        <a href="#workshops">
          <p>پیش ثبت نام</p>
        </a>
        <a href="#Team">
          <p>برگزارکنندگان</p>
        </a>
        <a href="#contact">
          <p>ارتباط با ما</p>
        </a>
      </ul>
    </div>
    <div class="background-img">
      <img :src="backgroundImg" alt="">
    </div>
    <div class="main-body">
      <!-- PRODUCTS -->
      <section class="top-title" id="workshops">
        <div class="svg-wrapper">
          <svg xmlns="http://www.w3.org/2000/svg">
            <rect class="shape"></rect>
          </svg>
          <h2 class="text"> Pre-Registering </h2>
        </div>
      </section>
      <div class="list">
        <div v-for="(workshop, index) in workshops" :key="`workshop-${index}`" class="product-for">
          <ProductComponent :workshop="workshop"></ProductComponent>
        </div>
      </div>
      <!-- STAFFS -->
      <section class="top-title" id="Team">
        <div class="svg-wrapper">
          <svg xmlns="http://www.w3.org/2000/svg">
            <rect class="shape"></rect>
          </svg>
          <h2 class="text"> Staff </h2>
        </div>
      </section>
      <div class="list">
        <div v-for="(staff, index) in staffs" :key="`staff-${index}`" class="staffs-for">
          <StaffComponent :staff="staff"></StaffComponent>
        </div>
      </div>
    </div>
    <footer>
      <div class="footer">
        <section class="contact-area" id="contact">
          <ul>
            <li><a class="hover-target" href="https://t.me/ESW_Support" target="_blank"><i class="fa fa-telegram"></i></a></li>
            <li><a class="hover-target" href="https://www.linkedin.com/in/resana-association/" target="_blank"><i
                class="fa fa-linkedin-square"></i></a></li>
            <li><a class="hover-target" href="https://instagram.com/Resana_Association" target="_blank"><i
                class="fa fa-instagram"></i></a></li>
            <li><a class="hover-target" href="mailto:Resana@ee.sharif.edu" target="_blank"><i
                class="fa fa-envelope"></i></a></li>
          </ul>
        </section>
      </div>
      <p>
        All rights reserved by
        <a href="https://ee.sharif.edu/~resana" target="_blank">
          ©Resana Association 2022
        </a>
      </p>
    </footer>
    <br> <br>
  </div>
</template>

<script>
import backgroundImg from '../statics/background.jpg'
import ProductComponent from "@/components/ProductComponent";
import StaffComponent from "@/components/StaffComponent";


export default {
  components: { ProductComponent, StaffComponent },
  data() {
    return {
      backgroundImg,
      workshops: [
        {name: 'ML', img: backgroundImg, expirationData: '31', price: '20000', payLink: 'https://idpay.ir/resana25esw/shop/574481'},
        {name: 'MATLAB', img: backgroundImg, expirationData: '1', price: '60000', payLink: 'https://idpay.ir/resana25esw/shop/574481'},
        {name: 'Web', img: backgroundImg, expirationData: '2', price: '30000', payLink: 'https://idpay.ir/resana25esw/shop/574481'}
      ],
      staffs: [
        {name: 'Yasin', img: backgroundImg, linkedin: 'https://www.linkedin.com/in/i4sin/', position: 'Head'},
        {name: 'Yasin', img: backgroundImg, linkedin: 'linkedin', position: 'Head'},
        {name: 'Yasin', img: backgroundImg, linkedin: 'linkedin', position: 'Head'},
        {name: 'Yasin', img: backgroundImg, linkedin: 'linkedin', position: 'Head'},
        {name: 'Yasin', img: backgroundImg, linkedin: 'linkedin', position: 'Head'}
      ]
    }
  }
}
</script>

<style scoped>
.header {
  display: flex;
  background-color: transparent;
  flex-direction: column;
  width: 100%;
  padding: 0 0 20px 0;
  z-index: 1000;
}


.header .navigation {
  display: flex;
  max-width: 100%;
  gap: 4%;
  padding: 0 20px 10px 20px;
  background-color: transparent;
}

.header .navigation > a {
  min-height: 30px;
  min-width: fit-content;
  width: 18%;
  padding: 1% 20px;
  background-color: rgba(var(--secondary-color-rgb), 0.25);
  color: var(--secondary-color);
  border-radius: 0 0 10px 10px;
  text-decoration:none;
}

.header .navigation > a > p {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: transparent;
  font-size: 2vw;
}

.background-img > img {
  width: 100%;
}

.main-body {
  display: flex;
  flex-direction: column;
  width: 100%;
  justify-content: center;
  align-items: center;
}

.main-body .top-title {
  display: flex;
  justify-content: center;
  background-color: transparent;
  margin: 50px 0;
}

.main-body .top-title .svg-wrapper {
  text-align: center;
  position: relative;
  /*transform: translateY(-50%);*/
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  height: fit-content;
  margin-right: auto;
  margin-left: auto;
  background-color:  transparent;
  color: var(--secondary-color);
}

.main-body .top-title .svg-wrapper > svg {
  width: max(40vw, 320px);
  height: 60px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.shape {
  text-align: center;
  width: max(40vw, 320px);
  height: 60px;
  stroke-dasharray: 150 calc(max(60vw,480px) + 60px - 75px);
  stroke-dashoffset: calc(max(60vw,480px) * -1 - 60px + 75px);
  stroke-width: 5px;
  fill: transparent;
  fill-opacity: 0;
  stroke: var(--tertiary-color);
  border-bottom: 4px solid white;
  transition: stroke-width 1s, stroke-dashoffset 1s, stroke-dasharray 1s;
}

.main-body .top-title .svg-wrapper .text {
  background-color: transparent;
  color: var(--secondary-color);
  top: 20px;
  position: absolute;
  text-align: center;
  font-weight: bold;
}

.main-body .top-title .svg-wrapper:hover .shape {
  fill: transparent;
  background-color: transparent;
  stroke-width: 5px;
  stroke-dashoffset: 0;
  stroke-dasharray: calc(max(80vw,640px) + 120px);
}

/* products */
/*.main-body .list {*/
/*  display: grid;*/
/*  flex-wrap: wrap;*/
/*  justify-content: center;*/
/*  text-align: center;*/
/*  padding-top: 3%;*/
/*  width: 100%;*/
/*}*/

@media (max-width: 500px) {
  .list {
    display: flex;
    flex-wrap: wrap;
    /*grid-template-columns: minmax(0, 1fr);*/
    /*padding: min(5%,30px) 5% 5% 5%;*/
    align-items: center;
    justify-content: center;
    width: 100%;
    gap: 25px;
  }
}

@media (min-width: 500px) {
  .list {
    display: flex;
    flex-wrap: wrap;
    /*grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));*/
    /*padding: min(5%,30px) 5% 5% 5%;*/
    justify-content: center;
    align-items: center;
    width: 100%;
    gap: 15px;
  }
}

.list .product-for {
  /*width: 100%;*/
  display: flex;
  justify-content: center;
  align-items: center;
}

.staffs-for {
  display: flex;
  justify-content: center;
  align-items: center;
}


.contact-area{

  background-color: #1b1e3f;
  display: flex;
  flex-direction: column;
  flex-wrap: wrap;
  justify-content: center;
}

.contact-area > img{
  height: 10%;
  width: 10%;
  margin-right: auto;
  margin-left: auto;
  margin-top: 20px;
}

.contact-area hr{
  width: 50%;
  margin-right: auto;
  margin-left: auto;
  margin-top: 50px;
}

.contact-area p{
  background-color: transparent; color: white; text-align: center; margin-top: 30px;
  margin-right: auto;
  margin-left: auto;
  width: 50%;
}

.contact-area ul{
  background-color: transparent;
  margin-right: auto;
  margin-left: auto;    font-size: 40px;
}


.contact-area ul li{
  float: left;
  margin-right: 10px;
  margin-left: 10px;
  margin-top: 30px;
  list-style: none;
  background-color: transparent;
}

.contact-area ul li  a{
  background-color: transparent;
  color: rgb(255, 255, 255);
}

.contact-area ul li  a i{
  background-color: transparent;
  color: rgb(255, 255, 255);
}
.contact-area ul li i:hover{
  background-color: transparent;
  margin-right: auto;
  margin-left: auto;     color: rgb(255, 208, 0);
}

footer{
  background-color: #1a1d3c; color: white; text-align: center; text-decoration: none;
}
footer a{
  background-color: transparent; color: white; text-decoration: none;
}
</style>