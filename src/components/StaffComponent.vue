<template>
  <div class="container">
    <a :href="staff.linkedin" target="_blank">
      <div class="box">
        <div class="imgBox">
          <img :src="staff.img" alt="">
        </div>
        <div class="content">
          <div class="hover-card">
            <div class="profile">
              <h2>{{ staff.name }}</h2>
              <h4>{{ staff.position }}</h4>
            </div>
          </div>
        </div>
      </div>
    </a>
  </div>
</template>

<script>
export default {
  props: {
    staff: {}
  }
}
</script>

<style scoped>
@media (max-width: 600px) {
  .container {
    padding-top: 4%;
    width: max(30vw, 280px);
    min-height: fit-content;
    justify-content: center;
    margin: 10px auto 10px auto;
    text-align: center;
  }
}

@media (min-width: 600px) {
  .container {
    padding-top: 4%;
    width: max(20vw, 280px);
    height: fit-content;
    justify-content: center;
    margin: 10px auto 10px auto;
    text-align: center;
  }
}

.container > a {
  display: flex;
  align-items: center;
  justify-content: center;
}

.container > a .box {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  position: relative;
  width: 200px;
  height: 300px;
  background: #000;
  box-shadow: 0 30px 30px rgba(0, 0, 0, .5);
  margin-right: 10px;
  margin-left: 10px;
  margin-bottom: 30px;
}

.container a > .box .imgBox {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  align-items: center;
}

.box .imgBox > img{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: 0.5s;
}

.box:hover .imgBox > img{
  opacity: 1;
}

.box .content{
  position: absolute;
  bottom: 20px;
  left: 10%;
  width: 80%;
  height: 60px;
  overflow: hidden;
  background-color: transparent;
  font-weight: bolder;
}

.box:hover .content {
  background-color: rgba(59, 59, 59, 0.705);
  transition: 0.5s;
  width: 100%;
  height: 100%;
  bottom: 0;
  left: 0;
  text-align: center;
}

.box .content > h3 {
  font-size: 24px;
}

.box:hover .content > h3{
  display: none;
}

.box .content .hover-card{
  opacity: 1;
  color: rgb(255, 255, 255);
  background-color: transparent;
}

.profile{
  background-color: transparent;
}

.profile h2{
  margin-top: 150px;
  color: rgb(255, 255, 255);
  width: 80%;
  margin-right: auto;
  margin-left: auto;
}

.profile h2, h4{
  text-align: center;
  background-color: transparent;
}
</style>