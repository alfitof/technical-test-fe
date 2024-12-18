<script>
export default {}
</script>

<template>
  <div class="footer-section">
    <div class="page-padding">
      <div class="spacer-xxhuge-top"></div>
      <div class="footer-wrapper">
        <div class="footer-cta-wrapper">
          <h6 class="heading-style-h1">
            <span class="red-text">Give us a problem</span><br />
            We will find the solution!
          </h6>
          <a href="#" class="button"> Get in touch </a>
        </div>

        <div class="footer-links">
          <div class="menu-button"><a href="#"> Home </a></div>
          <div class="menu-button"><a href="#"> Product development </a></div>
          <div class="menu-button"><a href="#"> Mechanical engineering </a></div>
          <div class="menu-button"><a href="#"> Vacancies </a></div>
          <div class="menu-button"><a href="#"> About Trios </a></div>
          <div class="menu-button"><a href="#"> Blog </a></div>
          <div class="menu-button"><a href="#"> Contact </a></div>
        </div>

        <!-- Kolom 3: Contact -->
        <div class="footer-contact">
          <p>Contact</p>
          <div class="contact">
            <a href="#">Nijverheidsweg 19NL-7161 AA Neede</a>
            <a href="tel:+31(0)545–280130">+31 (0) 545 — 280 130</a>
            <a href="mailto:info@trios.nl">info@trios.nl</a>
          </div>
          <div class="footer_social-list">
            <img src="../assets/images/download (1).svg" alt="" />
            <img src="../assets/images/download.svg" alt="" />
          </div>
        </div>
      </div>
      <div class="spacer-xxhuge-bot"></div>
      <div class="divider-footer"></div>
      <div class="footer_bottom-wrapper">
        <div>© Trios</div>
        <a href="#">Privacy</a>
        <a href="#">General terms and conditions</a>
        <a href="#">Cookies</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer-section {
  background-color: #fff;
  color: #333;
}

.page-padding {
  padding: 20px 100px;
}

.spacer-xxhuge-top {
  padding-top: 3rem;
}
.spacer-xxhuge-bot {
  padding-top: 5rem;
}

.footer-wrapper {
  grid-column-gap: 16px;
  grid-row-gap: 16px;
  grid-template-rows: auto;
  grid-template-columns: 1fr 1fr 1fr;
  grid-auto-columns: 1fr;
  display: grid;
}

.heading-style-h1 {
  font-size: 3.8rem;
  font-weight: bold;
  margin: 0;
  color: #2b3467;
}

.red-text {
  color: #eb455f;
}

.button {
  display: inline-block;
  margin-top: 3rem;
  background-color: #2b3467;
  color: white;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
}

.footer-links {
  grid-column-gap: 0.25rem;
  grid-row-gap: 0.25rem;
  flex-flow: column;
  justify-content: flex-start;
  align-items: flex-start;
  display: flex;
}

.menu-button {
  text-align: start;
  padding: 0.6rem 1.5rem;
}

.menu-button a {
  background-color: #dee7f4;
  padding: 0.6rem 1.1rem;
  border-radius: 8px;
  color: #2b3467;
  text-decoration: none;
}

.footer-contact {
  p {
    margin: 0 0 10px 0;
    font-size: 1.2rem;
    color: #2b3467;
  }

  .contact {
    display: flex;
    flex-direction: column;
    grid-row-gap: 1rem;

    a {
      color: #7c7f8d;
      text-decoration: none;

      &:hover {
        color: #2b3467;
      }
    }
  }
}

.footer_social-list {
  display: flex;
  gap: 10px;
  width: 30px;
  height: 30px;
  margin-top: 20px;

  img {
    filter: grayscale(100%);
    opacity: 0.5;
  }
}

.divider-footer {
  height: 1px;
  background-color: #ddd;
  margin-top: 20px;
}

.footer_bottom-wrapper {
  display: flex;
  justify-content: center;
  gap: 2rem;
  align-items: center;
  margin-top: 30px;
  margin-bottom: 15px;
  color: #7c7f8d;
  font-size: 0.9rem;
}

.footer_bottom-wrapper a {
  color: #7c7f8d;
  text-decoration: none;
}

/* Responsive: Hide "Give us a problem" on mobile and adjust layout */
@media (max-width: 1024px) {
  .footer-wrapper {
    grid-template-columns: 1fr 1fr;
  }

  .footer-cta-wrapper {
    display: none;
  }

  .footer_bottom-wrapper {
    visibility: hidden;
  }
}

@media (max-width: 640px) {
  .footer-wrapper {
    grid-template-columns: 1fr;
  }

  .page-padding {
    padding: 20px 50px;
  }

  .menu-button {
    padding: 0.6rem 0rem;
  }
}
</style>
