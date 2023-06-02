<template>
  <div id="main-banner">
    <h1>Crie seu Hamburguer!</h1>
    <div v-show="showScrollArrow" class="scroll-arrow" @click="scrollToNextSection">
    <i class="arrow"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "Banner",
  data() {
    return {
      showScrollArrow: true
    };
  },
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed() {
    window.removeEventListener("scroll", this.handleScroll);
  },
  methods: {
    handleScroll() {
      const bannerHeight = this.$el.offsetHeight;
      const scrollPosition = window.scrollY;

      if (scrollPosition > bannerHeight) {
        this.showScrollArrow = false;
      } else {
        this.showScrollArrow = true;
      }
    },
    scrollToNextSection() {
      const nextSection = document.querySelector("#next-section");

      if (nextSection) {
        const scrollToOptions = {
          top: nextSection.offsetTop,
          behavior: "smooth"
        };

        window.scrollTo(scrollToOptions);
        this.showScrollArrow = false;
      }
    }
  }
};
</script>


<style scoped>
#main-banner {
  background-image: url("/img/burguer_back.jpg");
  background-position: 0 -200px;
  background-size:cover;
  height: 725px;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  position: relative;
}

#main-banner h1 {
  color: #fff;
  text-align: center;
  font-size: 60px;
  background-color: #b68e0980;
  padding: 20px 40px;
}

.scroll-arrow {
  position: fixed;
  left: 50%;
  bottom: 20px;
  transform: translateX(-50%);
  width: 60px;
  height: 60px;
  background-color: #ccc;
  border-radius: 50%;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: arrowBounce 1.5s infinite alternate;
  transition: opacity 0.3s;
}


.scroll-arrow:hover {
  opacity: 0.7;
}

.scroll-arrow.hide {
  opacity: 0;
  pointer-events: none;
}

@keyframes arrowBounce {
  0% {
    transform: translateY(0);
  }
  100% {
    transform: translateY(10px);
  }
}

.arrow {
  border: solid #333;
  border-width: 0 3px 3px 0;
  display: inline-block;
  padding: 3px;
  transform: rotate(45deg);
}
</style>