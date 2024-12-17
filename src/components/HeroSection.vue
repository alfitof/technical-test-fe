<template>
  <section class="hero">
    <div class="gradient-logo"></div>
    <div class="overlay-hero"></div>
    <div class="hero-content">
      <h1><span class="highlight">Trios.</span> Reliable solutions for 30 years</h1>
    </div>
  </section>
</template>

<script>
export default {
  name: 'HeroSection',
}
</script>

<style lang="scss" scoped>
.hero {
  position: relative;
  background: url('https://cdn.prod.website-files.com/672cccfa55dcaee79acf45cf/674f102013bd946767c5ec28_Trios-Brandshoot-Liike-2700px-0402282.jpg')
    no-repeat center center/cover;
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: start;

  .gradient-logo {
    z-index: 3;
    background-color: #c7919100;
    background-image: radial-gradient(circle farthest-side at 10% -10%, #fff, #fff0 46%);
    position: absolute;
    inset: 0%;
  }

  .overlay-hero {
    cursor: none;
    mix-blend-mode: multiply;
    background-color: #2b346799;
    width: 100%;
    height: 100%;
    position: absolute;
    inset: 0%;
  }

  .hero-content {
    position: relative;
    text-align: left;
    margin-top: 2rem;
    margin-left: 6rem;
    width: 50%;
    max-width: 700px;
    z-index: 2;

    h1 {
      font-size: 80px;
      color: white;
      font-weight: normal;

      .highlight {
        color: #eb455f;
      }
    }
  }

  @media (max-width: 1024px) {
    .hero-content {
      margin-left: 0rem;
      margin-bottom: 3rem;
      width: 90%;
      max-width: 1200px;
      h1 {
        font-size: 41px;
      }
    }
  }
}
@media (max-width: 1024px) {
  .hero {
    justify-content: center;
    align-items: end;
  }
}
</style>
