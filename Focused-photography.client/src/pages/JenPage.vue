<template>
  <!-- jen -->
  <div class="container-fluid my-5">
    <div class="row justify-content-around">
      <div id="bag-click" class="click z-1" @click="bagTransition()">
        <p class="position-absolute pro-B-font t-xl mt-5">
          What's In My Bag?
        </p>
      </div>
      <div id="about-click" class="click z-1 mr-xl" @click="jenTransition()">
        <div>
          <p class="position-absolute city-font t-xxxl mt-3 ml-1">
            about
          </p>
          <p class="position-absolute pro-B-font t-xl mt-5 ml-4">
            JENNIFER
          </p>
        </div>
      </div>
    </div>
    <div class="row justify-content-center bg-white">
      <div id="bag" class="col-4 bag hide-bag">
        <img class="img-fluid" src="../assets/img/bag.png" alt="camera bag">
      </div>
      <div id="jen" class="self-img d-flex flex-column flex-wrap align-content-between">
        <img class="img-fluid jen" src="https://firebasestorage.googleapis.com/v0/b/focused-47421.appspot.com/o/static%20images%2Fself.jpg?alt=media&token=4847c646-8bb2-4ce9-a873-d8c0c5ebfeb7" alt="jen">
      </div>
      <div id="about-jen" class="col-4 hide-about about-jen">
        <p class="position-absolute text-focus-dark city-font t-xxxl mt-3 ml-1">
          about
        </p>
        <p class="position-absolute pro-B-font t-xl mt-5 ml-4">
          JENNIFER
        </p>
        <p class="mt-5 pt-5 neutra-font text-focus-dark">
          Lorem ipsum dolor, sit amet consectetur adipisicing elit. Consectetur neque natus tempora delectus quas
          voluptatum ducimus minus assumenda error, ullam eveniet deleniti perspiciatis dolores? Pariatur aspernatur qui
          perferendis quis odio. Lorem ipsum dolor sit amet consectetur adipisicing elit. Error excepturi molestias
          magni aliquam. Debitis sapiente magnam ut odio earum labore deleniti blanditiis saepe facere? Esse explicabo
          dolor soluta in expedita!
        </p>
      </div>
    </div>

    <div class="row bg-pink"></div>
  </div>
</template>

<script>
import { reactive } from '@vue/reactivity'
import $ from 'jquery'
export default {
  name: 'Jen',
  setup() {
    const state = reactive({
      jen: false,
      bag: false
    })
    return {
      state,
      bagTransition() {
        $('#bag').toggleClass('hide-bag')
        $('#jen').toggleClass('jen-bag')
        $('#bag-click').addClass('d-none')
        $('#about-click').addClass('d-none')
      },
      jenTransition() {
        $('#about-jen').toggleClass('hide-about')
        $('#jen').toggleClass('about-jen-self')
        $('#bag-click').addClass('d-none')
        $('#about-click').addClass('d-none')
      }
    }
  }
}
</script>

<style scoped lang="scss">
@import "../assets/scss/main.scss";
.bg-pink{
  height:60px;
}
.about-jen{
  transition: all 1.5s linear;
  position: absolute;
  left: 800px;
}
.hide-about{
  transition: all 1.5s linear;
  position: absolute;
  left: 1400px;
}
.jen{
  object-fit: cover;
  height: 60vh;
}
.self-img{
  transition: all 1s linear;
  position: relative;
  left: 0px;
  right: 0px;
}
.about-jen-self{
  transition: all 1s linear;
  position: relative;
  right: 200px
}
.jen-bag{
  transition: all 1s linear;
  position: relative;
  left: 200px
}
.bag{
  transition: all 1.5s linear;
  position: absolute;
  transform: scale(1.5);
  margin-top: 4rem;
  right: 700px;
}
.hide-bag{
  transition: all 1.5s linear;
  position: absolute;
  right: 1300px;
}
.z-1{
  z-index: 1;
}
.mr-xl{
  margin-right: 22vw;
}
.ml-xl{
  margin-left: 22vw;
}
</style>
