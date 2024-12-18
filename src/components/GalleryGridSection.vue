<script>
import { gsap } from 'gsap'
import ScrollTrigger from 'gsap/ScrollTrigger'

export default {
  mounted() {
    gsap.registerPlugin(ScrollTrigger)

    gsap.utils.toArray('.hover-text').forEach((item) => {
      item.addEventListener('mouseenter', () => {
        gsap.to(item.querySelector('.overlay'), {
          y: '0%',
          duration: 0.5,
          ease: 'power2.out',
        })
      })

      item.addEventListener('mouseleave', () => {
        gsap.to(item.querySelector('.overlay'), {
          y: '100%',
          duration: 0.5,
          ease: 'power2.out',
        })
      })
    })

    // Scroll-triggered animation for each row
    gsap.utils.toArray('.row').forEach((row, index) => {
      gsap.from(row, {
        y: 50,
        opacity: 0,
        duration: 1.5,
        ease: 'power2.out',
        scrollTrigger: {
          trigger: row,
          start: 'top 80%',
          end: 'top 20%',
          scrub: 0.5,
        },
      })
    })
  },
}
</script>

<template>
  <div class="title-wrapper">
    <div class="text-wrapper">
      <div class="text-dot"></div>
      <p class="text-intro is-dark">
        We zijn je productontwikkelaar, procesontwikkelaar en machinebouwer. We zijn het team dat
        naast je staat bij elke stap en helpt. Met prototypes, duurtesten, CE- en
        patentondersteuning, FEM berekeningen en projectmanagement.
      </p>
    </div>
  </div>
  <div class="gallery">
    <!-- Row 1 -->
    <div class="row">
      <div class="item hover-text">
        Prototype +
        <div class="overlay">
          We build prototypes and zero series in our workshop. Here we test whether the design does
          what it should do. High focus, speed and efficiency.
        </div>
      </div>
      <div class="item image">
        <img
          src="../assets/images/674f19d0d40cd4619b25bbce_Trios-Brandshoot-Liike-2700px-0402913.jpg"
          alt="Image 1"
        />
      </div>
      <div class="item hover-text">
        FEM Calculations +
        <div class="overlay">
          Build immediately? No. With FEM calculations, we foresee problems and see if we meet the
          conditions.
        </div>
      </div>
    </div>

    <!-- Row 2 -->
    <div class="row">
      <div class="item image">
        <img
          src="../assets/images/674f101f6504239e3308de24_Trios-Brandshoot-Liike-2700px-0402095.png"
          alt="Image 2"
        />
      </div>
      <div class="item hover-text">
        (Duration) tests +
        <div class="overlay">
          Prototypen, nulseries en onderdelen van machines controleren we zorgvuldig op maatvoering,
          continuïteit en slijtage.
        </div>
      </div>
      <div class="item image">
        <img src="../assets/images/67592feec8d5860d47440b2a_Kern CNC klem.jpg" alt="Image 3" />
      </div>
    </div>

    <!-- Row 3 -->
    <div class="row">
      <div class="item image">
        <img
          src="../assets/images/674f19d030f97a84931c671c_Trios-Brandshoot-Liike-2700px-0401835.jpg"
          alt="Image 4"
        />
      </div>
      <div class="item hover-text">
        Project Management +
        <div class="overlay">
          We like to work together intensively and aim for long-term relationships in every project.
          Good project management is part of that.
        </div>
      </div>

      <div class="item image">
        <img src="../assets/images/6737224a196dc6346f8ab027_Market Image-2.jpg" alt="Image 4" />
      </div>
    </div>
  </div>
</template>
<style lang="scss" scoped>
.gallery {
  background: #ecf5ff;
  padding: 4rem;
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 0;
}

.row {
  display: contents;
}

.item {
  position: relative;
  color: #2b3467;
}

.item img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.hover-text {
  display: flex;
  justify-content: flex-start;
  align-items: flex-end;
  background-color: #fff;
  padding: 10px;
  position: relative;
  overflow: hidden;
}

.hover-text .overlay {
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #2b3467;
  color: white;
  text-align: left;
  padding: 15px;
  transform: translateY(100%);
  display: flex;
  align-items: flex-end;
}

.overlay div {
  white-space: normal;
  line-height: 1.5;
}
.title-wrapper {
  grid-column-gap: 16px;
  grid-row-gap: 16px;
  grid-template-rows: auto;
  grid-template-columns: 1fr 1fr;
  grid-auto-columns: 1fr;
  display: grid;
  background: #ecf5ff;
  padding-top: 4rem;
  padding-bottom: 0rem;
  padding-left: 4rem;
  padding-right: 4rem;
}
.text-wrapper {
  display: flex;
  position: relative;
}
.text-dot {
  background-color: #eb455f;
  width: 0.375rem;
  height: 0.375rem;
  display: block;
  position: absolute;
  inset: 2rem auto 0% 0%;
}
.text-intro {
  text-indent: 1.5rem;
  font-size: 1.15rem;
  color: #2b3467b3;
  line-height: 170%;
  margin-bottom: 0;
}

@media screen and (max-width: 1024px) {
  .title-wrapper {
    grid-template-columns: 1fr;
  }
  .gallery {
    grid-template-columns: 1fr;
  }
}
</style>
