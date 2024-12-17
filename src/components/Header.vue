<template>
  <header class="header">
    <img src="../assets/images/download (3).svg" alt="Logo" />
    <nav class="navigation" :class="{ 'nav-active': isMenuActive }">
      <a href="#" class="nav-item">Home</a>
      <a href="#" class="nav-item">Product development</a>
      <a href="#" class="nav-item">Mechanical engineering</a>
      <a href="#" class="nav-item">Vacancies</a>
      <a href="#" class="nav-item">About Trios</a>
      <a href="#" class="nav-item">Contact</a>
      <div class="nav-item locales-button">
        <img src="../assets/images/6744812e2d44005ba3ac9d47_Engels.svg" />
        <img src="../assets/images/download (5).svg" />
      </div>
    </nav>

    <!-- Overlay for background blur -->
    <div v-if="isMenuActive" class="overlay"></div>

    <!-- Hamburger menu -->
    <div class="hamburger" @click="toggleMenu" :class="{ active: isMenuActive }">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>
</template>

<script>
export default {
  name: 'HeaderComponent',
  data() {
    return {
      isMenuActive: false,
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuActive = !this.isMenuActive
    },
  },
}
</script>

<style lang="scss" scoped>
.header {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  max-width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 2.4rem 6rem;
  z-index: 10;
  background: transparent;
  color: white;
  box-sizing: border-box;
  transition: padding 0.3s ease-in-out;

  .navigation {
    display: flex;
    gap: 0.25rem;
    transition: transform 0.3s ease-in-out;

    .nav-item {
      display: flex;
      justify-content: center;
      align-items: center;
      text-decoration: none;
      color: #2b3467;
      background-color: white;
      font-weight: 500;
      font-size: 16px;
      padding: 0.57rem 1.19rem;
      transition: color 0.3s;
      text-align: center;
      border-radius: 0.5rem;

      &:hover {
        color: #e74c3c;
      }
    }

    .locales-button {
      display: flex;
      align-items: center;
      gap: 0.1rem;
      cursor: pointer;
    }
  }

  .hamburger {
    background: #2b3467;
    padding: 10px;
    border-radius: 7px;
    display: none;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    width: 23px;
    height: 19px;
    cursor: pointer;
    z-index: 15;
    transition: all 0.3s ease;

    span {
      display: block;
      width: 100%;
      height: 2px;
      background-color: rgb(214, 214, 214);
      border-radius: 5px;
      transition: all 0.3s ease;
    }

    &.active {
      span:nth-child(1) {
        transform: rotate(45deg);
        position: relative;
        top: 8px;
      }

      span:nth-child(2) {
        opacity: 0;
      }

      span:nth-child(3) {
        transform: rotate(-45deg);
        position: relative;
        top: -8px;
      }
    }
  }

  @media (max-width: 1024px) {
    .navigation {
      display: none; /* Hide desktop navigation for mobile */
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: white;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 2rem;
      width: 70%; /* Set the width to make it wider */
      max-width: 400px; /* Optional: adjust the maximum width */
      border-radius: 1rem;
      z-index: 20;
      opacity: 0;
      transition: opacity 0.3s ease-in-out;
    }

    .navigation.nav-active {
      display: flex;
      opacity: 1;
    }

    .hamburger {
      display: flex;
    }

    /* Overlay for background blur */
    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5); /* Slight black overlay */
      backdrop-filter: blur(5px); /* Apply the blur effect */
      z-index: 10;
    }
  }
}

@media (max-width: 1024px) {
  .header {
    padding: 2.2rem;
  }
}
</style>
