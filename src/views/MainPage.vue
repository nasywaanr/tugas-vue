<template>
    <div>
      <!-- Page Counter -->
      <div class="container text-center mt-4">
        <h2>Counter</h2>
        <div class="my-3">
          <h1>{{ count }}</h1>
          <button @click="increaseCounter" class="btn btn-success">Increase</button>
          <button @click="decreaseCounter" class="btn btn-danger">Decrease</button>
        </div>
      </div>
  
      <!-- Change Color -->
      <div class="container text-center mt-4">
        <h2>Change Color</h2>
        <div class="d-flex justify-content-center">
          <div class="col-md-5">
            <div class="color-box" :style="{ backgroundColor: selectedColor }"></div>
            <button @click="changeRandomColor" class="btn btn-dark btn-sm mt-2">Change Random color</button>
          </div>
        </div>
      </div>
  
      <!-- Carousel inside a Card -->
      <div class="container mt-5">
        <h2 class="text-center">Carousel</h2>
        <div class="card" style="width: 18rem; margin: 0 auto;">
          <div id="carouselExample" class="carousel slide" data-ride="carousel">
            <div class="carousel-inner">
              <div class="carousel-item" :class="{ active: slide === 0 }">
                <img src="https://i.pinimg.com/originals/2d/23/5f/2d235f733c7fd7553ff283646bdf5bd1.png"
                  class="d-block w-100" alt="First Slide">
              </div>
              <div class="carousel-item" :class="{ active: slide === 1 }">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSMk8dMpHR2Pdn2GXAjkIH8eX-Nbkb8aV7ZGg&s"
                  class="d-block w-100" alt="Second Slide">
              </div>
              <div class="carousel-item" :class="{ active: slide === 2 }">
                <img
                  src="https://img.freepik.com/premium-photo/beautiful-pixel-art-illustration-japanese-village-night_14117-372835.jpg"
                  class="d-block w-100" alt="Third Slide">
              </div>
            </div>
            <a class="carousel-control-prev" href="#" role="button" @click="prevSlide">
              <span class="carousel-control-prev-icon" aria-hidden="true"></span>
              <span class="sr-only">Previous</span>
            </a>
            <a class="carousel-control-next" href="#" role="button" @click="nextSlide">
              <span class="carousel-control-next-icon" aria-hidden="true"></span>
              <span class="sr-only">Next</span>
            </a>
          </div>
          <!-- <div class="card-body">
            <h5 class="card-title">Pixel Art Carousel</h5>
          </div> -->
        </div>
      </div>
    </div>
  </template>
  
  <script>
    export default {
      data() {
        return {
          count: 0,
          slide: 0,
          randomColor: ["#C8102E", "#005aff", "#D79FC7", "#81BE83", "#96AED0", "#133955"],
          selectedColor: "FFFFFF"
        };
      },
      methods: {
        increaseCounter() {
          this.count++;
        },
        decreaseCounter() {
          if (this.count > 0) this.count--;
        },
        changeRandomColor() {
          const randomIndex = Math.floor(Math.random() * this.randomColor.length);
          this.selectedColor = this.randomColor[randomIndex]
        },
        nextSlide() {
          if (this.slide < 2) {
            this.slide++;
          } else {
            this.slide = 0;
          }
        },
        prevSlide() {
          if (this.slide > 0) {
            this.slide--;
          } else {
            this.slide = 2;
          }
        },
      },
    };
  </script>
  
  <style scoped>
    .color-box {
      width: 100px;
      height: 100px;
      background-color: white;
      border: 2px solid #333;
      margin: 0 auto;
      border-radius: 5px;
    }
  </style>
g  