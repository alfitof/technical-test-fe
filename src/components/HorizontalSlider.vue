<script>
import { gsap } from 'gsap'
import { ScrollTrigger } from 'gsap/ScrollTrigger'

export default {
  mounted() {
    gsap.registerPlugin(ScrollTrigger)

    let horizontalSections = gsap.utils.toArray('.container')

    horizontalSections.forEach((container) => {
      let sections = container.querySelectorAll('.panel')

      gsap.to(sections, {
        xPercent: -100 * (sections.length - 1),
        ease: 'none',
        scrollTrigger: {
          trigger: container,
          pin: true,
          scrub: 1,
          start: 'top top',
          end: '+=3000',
        },
      })
    })
  },
}
</script>

<template>
  <div>
    <div class="container">
      <section class="panel red">
        <div class="content">
          <p>
            Trios is strong in conceptual thinking; dividing a big problem into bite-sized problems
            and merging the sum of the small problems into a working whole.
          </p>
          <p>
            De oplossingen zijn verrassend en altijd goed doordacht. Ideeën en concepten worden
            intern besproken met meerdere disciplines voordat ze aan de klant worden gepresenteerd.
          </p>
          <p>
            Tijdens de ontwikkeling van transportoplossingen wordt uitgebreid gerekend en
            gesimuleerd. Dit proces geeft veel vertrouwen in de uiteindelijke resultaten.
          </p>
          <p><strong>- René</strong></p>
        </div>
      </section>

      <section class="panel">
        <div class="image-container">
          <img
            src="../assets/images/674f1021ce2fff6650f6b3ab_Trios-Brandshoot-Liike-2700px-0402377.jpg"
            alt="Trios Brandshoot"
          />
        </div>
      </section>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.container {
  display: flex;
  flex-wrap: nowrap;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.panel {
  flex: 0 0 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.2rem;
  padding: 2rem;
  text-align: center;
  color: white;
}

.panel.red {
  background-color: #eb455f;
}

.panel.red .content {
  max-width: 70%;
  font-size: 1.5rem;
  line-height: 1.6;
}

.image-container {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
}

.image-container img {
  width: 100%;
  height: auto;
  object-fit: cover;
}
</style>
