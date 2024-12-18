<script>
export default {}
</script>

<template>
  <div class="intro-section">
    <div class="content-wrapper">
      <div class="spacer-large"></div>
      <div class="intro-grid">
        <div class="intro-text-container">
          <div class="dot-indicator"></div>
          <p class="intro-text is-white">
            For 30 years, our team has treated every project as if it were our own, with a great
            sense of responsibility. About the result, about your budget and your secrets. We
            realize what your company really needs and ensure that the solution stands like a
            stone.<br /><br />We combine experience in various sectors and craftsmanship into
            customized solutions. In this, we go further than simply executing; we think along and
            always keep your interests in mind. That is where our strength lies. Trust in solutions
            that go beyond demand.
          </p>
        </div>
      </div>
      <div class="spacer-large"></div>
    </div>
    <div class="section-divider">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 1440 78"
        fill="none"
        preserveAspectRatio="xMidYMid meet"
        style="display: block; line-height: 0"
      >
        <path
          fill-rule="evenodd"
          clip-rule="evenodd"
          d="M407.949 0C401.35 0 396 5.34991 396 11.9494V32C396 38.6274 390.627 44 384 44H0V78H396H412H1440V0H407.949Z"
          fill="#ECF5FF"
        ></path>
      </svg>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.intro-section {
  background-color: #2b3467;
}

.content-wrapper {
  align-self: center;
  margin-left: auto;
  margin-right: auto;
  padding-left: 7%;
  padding-right: 7%;

  .spacer-large {
    width: 100%;
    padding-top: 10rem;
  }

  .intro-grid {
    grid-column-gap: 1rem;
    grid-row-gap: 1rem;
    grid-template-rows: auto;
    grid-template-columns: 1.25fr 1.25fr 5.75rem;
    grid-auto-columns: 1fr;
    display: grid;

    .intro-text-container {
      display: flex;
      position: relative;
      grid-area: 1/2/2/3;

      .dot-indicator {
        background-color: #eb455f;
        width: 0.375rem;
        height: 0.375rem;
        display: block;
        position: absolute;
        inset: 2.1rem auto 0% 0%;
      }
      .intro-text {
        text-indent: 1.5rem;
        font-size: 1.25rem;
        color: #fff;
        margin-bottom: 0;
        line-height: 170%;
      }
    }
  }
}

@media (max-width: 1024px) {
  .content-wrapper {
    padding-left: 3rem;
    padding-right: 3rem;

    .spacer-large {
      padding-top: 8rem;
    }
    .intro-grid {
      grid-template-columns: 1.25fr;
      .intro-text-container {
        grid-area: span 1 / span 1 / span 1 / span 1;
        .intro-text {
          font-size: 1rem;
        }
      }
    }
  }
  .section-divider {
    width: 100%;
    display: block;
    position: relative;
  }
}
</style>
