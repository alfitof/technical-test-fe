<script>
export default {}
</script>

<template>
  <div class="vacatures-padding">
    <div class="vacatures-wrapper">
      <div class="images-blok">
        <div id="text1" class="text-block">
          <p class="text-size-medium">27 vacation days, and a well-arranged pension.</p>
        </div>
        <div id="text2" class="text-block second">
          <p class="text-size-medium">Daily coffee time at 10 a.m.</p>
        </div>
        <div id="img-blok" class="img-blok">
          <div class="img-dot"></div>
          <img
            loading="lazy"
            src="https://cdn.prod.website-files.com/672cccfa55dcaee79acf45cf/674f05b080a2a1e4d9db5e64_Trios-Brandshoot-Liike-2700px-0401711.webp"
            alt=""
            class="image-vacatures"
          />
        </div>
        <div id="img-blok2" class="img-blok">
          <div class="img-dot"></div>
          <img
            loading="lazy"
            src="https://cdn.prod.website-files.com/672cccfa55dcaee79acf45cf/674f101f47629be28a7a68cd_Trios-Brandshoot-Liike-2700px-0401540.jpg"
            alt=""
            class="image-vacatures"
          />
        </div>
        <div id="img-blok3" class="img-blok hide-tablet">
          <div class="img-dot"></div>
          <img
            loading="lazy"
            src="https://cdn.prod.website-files.com/672cccfa55dcaee79acf45cf/674f101e2f24ec777d237fd0_Trios-Brandshoot-Liike-2700px-0401453.jpg"
            alt=""
            class="image-vacatures"
          />
        </div>
      </div>
      <div class="vacatures-content">
        <h5 class="heading-style-h5">
          Our people are our driving force. We value young talent and experienced professionals. We
          are happy to invest in that. Also working for a company where your passion for the
          profession is central and seen? We are always looking for more talent.
        </h5>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.vacatures-padding {
  background: #ecf5ff;
  align-self: center;
  margin-left: auto;
  margin-right: auto;
  padding-right: 7%;
  overflow: hidden;
}
.vacatures-wrapper {
  grid-column-gap: 1rem;
  grid-row-gap: 1rem;
  grid-template-rows: auto;
  grid-template-columns: 1.5fr 1fr;
  grid-auto-columns: 1fr;
  display: grid;
}
.images-blok {
  grid-template-rows: auto auto;
  grid-template-columns: auto auto auto;
  grid-auto-columns: 1fr;
  justify-content: end;
  width: 100%;
  display: grid;
  overflow: hidden;
  justify-self: end;
}
.text-block {
  width: 19rem;
  padding: 1.5rem;
}
#text1 {
  grid-area: 1/2/2/3;
  align-self: end;
}
#text2 {
  grid-area: 2/3/3/4;
  align-self: start;
}
.text-size-medium {
  font-size: 1.25rem;
  text-decoration: none;
  color: #7c7f8d;
  line-height: 170%;
}
.img-blok {
  aspect-ratio: 1;
  width: 19rem;
  display: flex;
  position: relative;
  overflow: hidden;
}
#img-blok {
  grid-area: 1/1/2/2;
}
#img-blok2 {
  grid-area: 2/2/2/2;
}
#img-blok3 {
  grid-area: 1/3/2/4;
}
.img-dot {
  background-color: #ecf5ff;
  width: 0.7645rem;
  height: 0.7645rem;
  position: absolute;
  inset: 0% 0% auto auto;
}

.image-vacatures {
  object-fit: cover;
  width: 100%;
  height: 100%;
  max-width: 100%;
  display: inline-block;
  border: 0;
}
.hide-tablet {
  grid-area: 1/3/2/4;
}

.vacatures-content {
  width: 100%;
  padding-left: 3rem;
  align-self: end;
}
.heading-style-h5 {
  font-size: 1.5rem;
  font-family: Ppneuemontreal, Arial, sans-serif;
  font-weight: 500;
  line-height: 140%;
  color: #2b3467;
}

@media screen and (max-width: 1024px) {
  .vacatures-padding {
    padding-right: 0;
  }
  .vacatures-wrapper {
    grid-template-columns: 1.5fr;
  }
  .images-blok {
    grid-column-gap: 1rem;
    grid-row-gap: 1rem;
    flex-flow: column;
    grid-template-rows: auto auto auto auto;
    grid-template-columns: auto;
    grid-auto-columns: 1fr;
    justify-content: stretch;
    margin-left: auto;
    margin-right: auto;
    padding-left: 3rem;
    padding-right: 3rem;
    display: grid;
  }
  .text-block {
    width: 100%;
    padding-left: 0;
    padding-right: 0;
  }

  .text-block.second {
    padding-top: 1rem;
    padding-bottom: 1rem;
    grid-area: 2/3/3/4;
    align-self: start;
  }
  .img-blok {
    width: 100%;
    grid-area: 1/1/2/2;
  }
  .hide-tablet {
    display: none !important;
    grid-area: 1/1/2/2;
  }
  .vacatures-content {
    padding-bottom: 2rem;
    padding-left: 3rem;
    padding-right: 3rem;
  }
  .heading-style-h5 {
    font-size: 1.25rem;
  }
}
</style>
