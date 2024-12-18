<script>
import { gsap } from 'gsap'

export default {
  mounted() {
    this.incrementNumbers()
    this.scrollFadeEffect()
  },
  methods: {
    incrementNumbers() {
      const numbers = [
        { elementId: 'years-experience', value: 30 },
        { elementId: 'projects', value: 50 },
        { elementId: 'professionals', value: 16 },
      ]

      numbers.forEach(({ elementId, value }) => {
        gsap.to(`#${elementId}`, {
          innerHTML: value,
          duration: 5,
          ease: 'none',
          snap: { innerHTML: 1 },
        })
      })
    },

    scrollFadeEffect() {
      gsap.utils.toArray('.statistik').forEach((el) => {
        gsap.fromTo(
          el,
          { opacity: 0, y: 50 },
          {
            opacity: 1,
            y: 0,
            scrollTrigger: {
              trigger: el,
              start: 'top 80%',
              end: 'top 60%',
              scrub: 1,
            },
          },
        )
      })
    },
  },
}
</script>

<template>
  <div class="section-statistik">
    <div class="page-padding">
      <div class="spacer-xxhuge"></div>
      <div class="statistik-wrapper">
        <div class="statistik-content">
          <h2 class="heading-style-h2">Reliability at Trios: facts that speak</h2>
          <p class="text-size-medium text-gray">
            We focus on trust, innovation and craftsmanship. We'd love to tell you about that, but
            the facts speak for themselves.
          </p>
          <div class="statistik">
            <div data-gsap="el.6" class="statistik-item">
              <div id="years-experience" class="heading-style-h2">0</div>
              <p class="text-size-regular text-blue">Years of experience</p>
              <p class="text-size-small text-dark-gray">in precision engineering solutions.</p>
            </div>
            <div data-gsap="el.6" class="statistik-item">
              <div id="projects" class="heading-style-h2">0</div>
              <p class="text-size-regular text-blue">Projects</p>
              <p class="text-size-small text-dark-gray">in various sectors</p>
            </div>
            <div data-gsap="el.6" class="statistik-item">
              <div id="professionals" class="heading-style-h2">0</div>
              <p class="text-size-regular text-blue">young and experienced</p>
              <p class="text-size-small text-dark-gray">professionals</p>
            </div>
          </div>
        </div>
      </div>
      <div class="spacer-xxhuge"></div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.section-statistik {
  background: #ecf5ff;
  padding-left: 6.5rem;
  padding-right: 6.5rem;
  position: relative;
}
.page-padding {
  align-self: center;
  margin-left: auto;
  margin-right: auto;
  padding-left: 7%;
  padding-right: 7%;
}
.spacer-xxhuge {
  width: 100%;
  padding-top: 10rem;
}
.statistik-wrapper {
  grid-column-gap: 1rem;
  grid-row-gap: 1rem;
  grid-template-rows: auto;
  grid-template-columns: 1.25fr 1.25fr 5.75rem;
  grid-auto-columns: 1fr;
  display: grid;
}
.statistik-content {
  grid-area: 1/2/2/3;
}
.heading-style-h2 {
  color: #2b3467;
  font-size: 2.5rem;
  font-weight: 500;
}
.spacer-small {
  width: 100%;
  padding-top: 1rem;
}
.spacer-large {
  padding-top: 2.5rem;
}
.text-gray {
  color: #7c7d8f;
}
.text-dark-gray {
  color: #525b85b3;
}
.text-size-medium {
  font-size: 1.15rem;
  text-decoration: none;
  line-height: 170%;
  margin-bottom: 1rem;
}
.statistik {
  grid-column-gap: 8px;
  grid-row-gap: 8px;
  grid-template-rows: auto auto;
  grid-template-columns: 1fr 1fr;
  grid-auto-columns: 1fr;
  display: grid;
}
.statistik-item {
  background-color: #fff;
  border-radius: 0.5rem;
  padding: 1rem;
}

.text-blue {
  color: #2b3467;
}
.text-size-regular {
  font-size: 1.1rem;
  line-height: 170%;
}
.text-size-small {
  font-size: 0.9rem;
  line-height: 150%;
}

@media screen and (max-width: 1024px) {
  .section-statistik {
    padding-left: 3rem;
    padding-right: 3rem;
  }
  .spacer-xxhuge {
    padding-top: 8rem;
  }
  .statistik-wrapper {
    grid-template-columns: 1.25fr;
  }
  .statistik-content {
    grid-area: span 1 / span 1 / span 1 / span 1;
  }
  .heading-style-h2 {
    font-size: 2rem;
  }
  .spacer-large {
    padding-top: 1.5rem;
  }
  .heading-style-h2 {
    font-size: 2rem;
  }
  .spacer-xxhuge {
    padding-top: 8rem;
  }
}
</style>
