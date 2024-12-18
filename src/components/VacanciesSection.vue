<template>
  <div>
    <div class="section-vacancy scroll-trigger">
      <div class="spacer-xxhuge-vacancy"></div>
      <h3 class="heading-style-h6-vacancy">Vacancies</h3>
      <div class="spacer-small-vacancy"></div>
      <section class="vacatures-section">
        <div class="vacatures-grid">
          <div class="vacature-card">
            <a href="#" class="vacature-link"></a>
            <div class="vacatures-card-wrapper">
              <p class="text-size-large">Toolmaker with CNC experience</p>
              <p class="text-size-medium text-gray">
                Do you have an eye for detail, problem solving skills and, as a real professional,
                are you always looking for quality? This toolmaker/instrument maker vacancy is for
                you.
              </p>
              <div class="vacatures-card-details">
                <div class="vacature-detail-item">
                  <div class="vacature-dot"></div>
                  <p class="text-size-medium text-blue">Neede</p>
                </div>
                <div class="vacature-detail-item">
                  <div class="vacature-dot"></div>
                  <p class="text-size-medium text-blue">Full-Time</p>
                </div>
                <div class="vacature-detail-item">
                  <div class="vacature-dot"></div>
                  <p class="text-size-medium text-blue">MBO</p>
                </div>
              </div>
            </div>
            <div class="img-dot"></div>
            <div class="vacature-overlay"></div>
          </div>
          <div class="vacature-card">
            <a href="#" class="vacature-link"></a>
            <div class="vacatures-card-wrapper">
              <p class="text-size-large">Office environment cleaner</p>
              <p class="text-size-medium text-gray">
                Will you keep our pleasant working environment clean? Then you'll never work alone!
                This is the job for you.
              </p>
              <div class="vacatures-card-details">
                <div class="vacature-detail-item">
                  <div class="vacature-dot"></div>
                  <p class="text-size-medium text-blue">Neede</p>
                </div>
                <div class="vacature-detail-item">
                  <div class="vacature-dot"></div>
                  <p class="text-size-medium text-blue">18/24 hours a month</p>
                </div>
                <div class="vacature-detail-item">
                  <div class="vacature-dot"></div>
                  <p class="text-size-medium text-blue">No training required</p>
                </div>
              </div>
            </div>
            <div class="img-dot"></div>
            <div class="vacature-overlay"></div>
          </div>
        </div>
      </section>
      <div class="spacer-huge-vacancy"></div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style scoped>
.section-vacancy {
  background: #ecf5ff;
  padding-left: 6.5rem;
  padding-right: 6.5rem;
  z-index: 1;
  position: relative;
}
.page-padding {
  align-self: center;
  margin-left: auto;
  margin-right: auto;
  padding-left: 7%;
  padding-right: 7%;
}
.spacer-xxhuge-vacancy {
  width: 100%;
  padding-top: 10rem;
}

.heading-style-h6-vacancy {
  font-family: Ppneuemontreal, Arial, sans-serif;
  color: #2b3467;
  font-size: 1.25rem;
  font-weight: 500;
  line-height: 140%;
}

.spacer-small-vacancy {
  width: 100%;
  padding-top: 1rem;
}

.vacatures-card-details {
  grid-column-gap: 1.5rem;
  grid-row-gap: 1.5rem;
  justify-content: flex-start;
  align-items: center;
  display: flex;
}

.vacature-detail-item {
  grid-column-gap: 0.75rem;
  grid-row-gap: 0.75rem;
  justify-content: flex-start;
  align-items: center;
  display: flex;
}

.vacature-dot {
  background-color: #eb455f;
  width: 0.375rem;
  height: 0.375rem;
}
.vacatures-grid {
  grid-column-gap: 16px;
  grid-row-gap: 16px;
  grid-template-rows: auto;
  grid-template-columns: 1fr 1fr;
  grid-auto-columns: 1fr;
  display: grid;
}
.vacature-card {
  background-color: #fff;
  padding: 2rem;
  position: relative;
  overflow: hidden;
}

.vacature-link {
  z-index: 2;
  position: absolute;
  inset: 0%;

  max-width: 100%;
  display: inline-block;
}

.vacatures-card-wrapper {
  z-index: 1;
  position: relative;
}

.text-size-large {
  font-size: 1.5rem;
  color: #2b3467;
}

.spacer-xsmall {
  width: 100%;
  padding-top: 0.5rem;
}
.text-size-medium {
  font-size: 1.1rem;
  line-height: 170%;
  text-decoration: none;
}

.text-gray {
  color: #7c7f8d;
}

.text-blue {
  color: #2b3467;
}

.img-dot {
  background-color: #ecf5ff;
  width: 0.7645rem;
  height: 0.7645rem;
  z-index: 99;
  position: absolute;
  inset: 0% 0% auto auto;
}

.spacer-huge-vacancy {
  width: 100%;
  padding-top: 6rem;
}

.vacature-overlay {
  background-color: #dee7f4;
  position: absolute;
  inset: 0;
  transform: translateY(100%);
  transition: transform 0.3s ease-in-out;
}

.vacature-card:hover .vacature-overlay {
  transform: translateY(0);
}

@media (max-width: 1024px) {
  .vacatures-grid {
    grid-template-columns: 1fr;
  }
}
</style>
