<script>
import { gsap } from 'gsap'

export default {
  name: 'HeaderComponent',
  data() {
    return {
      isMenuActive: false,
      isScrolled: false,
      isDropdownActive: false,
      menuItems: [
        'Home',
        'Product development',
        'Mechanical engineering',
        'Vacancies',
        'About Trios',
        'Contact',
      ],
    }
  },
  methods: {
    toggleMenu() {
      this.isMenuActive = !this.isMenuActive
      if (this.isMenuActive) {
        this.animateMenuIn()
      }
    },
    animateMenuIn() {
      gsap.fromTo(
        this.$refs.navItems,
        { opacity: 0, y: -20 },
        { opacity: 1, y: 0, stagger: 0.1, duration: 0.5, ease: 'power2.out' },
      )
    },
    handleScroll() {
      this.isScrolled = window.scrollY > 50
    },
    toggleDropdown() {
      this.isDropdownActive = !this.isDropdownActive
    },
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeDestroy() {
    window.removeEventListener('scroll', this.handleScroll)
  },
}
</script>

<template>
  <header class="header" :class="{ scrolled: isScrolled }">
    <img
      src="../assets/images/download (3).svg"
      alt="Logo"
      class="logo"
      :class="{ scrolled: isScrolled }"
    />
    <nav class="navigation" :class="{ 'nav-active': isMenuActive }">
      <a
        v-for="(menu, index) in menuItems"
        :key="index"
        ref="navItems"
        href="#"
        class="nav-item hover-item"
        :class="{ scrolled: isScrolled }"
      >
        {{ menu }}
      </a>
      <div class="locales-button" @click="toggleDropdown">
        <img src="../assets/images/6744812e2d44005ba3ac9d47_Engels.svg" />
        <img src="../assets/images/download (5).svg" />
        <div v-if="isDropdownActive" class="dropdown-content">
          <div class="dropdown-item">
            <img src="../assets/images/6744812e2d44005ba3ac9d47_Engels.svg" />
            <p>English</p>
          </div>
          <div class="dropdown-item">
            <img src="../assets/images/674480fad4fc2c1bef58e509_Nederlands.svg" />
            <p>Nederlands</p>
          </div>
        </div>
      </div>
      <div class="locales-button-mobile">
        <img src="../assets/images/6744812e2d44005ba3ac9d47_Engels.svg" alt="English" />
        <img src="../assets/images/674480fad4fc2c1bef58e509_Nederlands.svg" alt="Nederlands" />
      </div>
    </nav>

    <div v-if="isMenuActive" class="overlay"></div>

    <div class="hamburger" @click="toggleMenu" :class="{ active: isMenuActive }">
      <span></span>
      <span></span>
      <span></span>
    </div>
  </header>
</template>

<style lang="scss" scoped>
.header {
  position: fixed;
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
  transition: all 0.3s ease-in-out;

  &.scrolled {
    background-color: white;
    padding: 1.2rem 6rem;
  }

  .navigation {
    display: flex;
    gap: 0.25rem;
    transition: transform 0.3s ease-in-out;

    .nav-item {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      text-decoration: none;
      color: #2b3467;
      background-color: white;
      font-weight: 500;
      font-size: 16px;
      padding: 0.57rem 1.19rem;
      text-align: center;
      border-radius: 0.5rem;
      transition:
        color 0.3s,
        background-color 0.3s;
      z-index: 10;

      &::after {
        content: '';
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: #dee7f4;
        transform: scaleY(0);
        transform-origin: bottom;
        transition: transform 0.3s ease-in-out;
        border-radius: 0.5rem;
        z-index: -1;
      }

      &:hover::after {
        transform: scaleY(1);
      }

      &.scrolled {
        background-color: #dee7f4;
      }
    }

    .hover-item {
      overflow: hidden;
    }

    .locales-button {
      position: relative;
      display: flex;
      justify-content: center;
      align-items: center;
      text-decoration: none;
      cursor: pointer;
      background-color: white;
      font-weight: 500;
      font-size: 16px;
      padding: 0.57rem 0.8rem 0.57rem 1.19rem;
      text-align: center;
      border-radius: 0.5rem;

      img {
        margin-left: 0.1rem;
      }

      .dropdown-content {
        display: block;
        position: absolute;
        top: 100%;
        left: 0;
        background-color: white;
        box-shadow: 0 8px 16px rgba(0, 0, 0, 0.2);
        width: 140px;
        border-radius: 8px;
        z-index: 20;
        padding: 10px 0;
        margin-top: 5px;
      }

      .dropdown-item {
        display: flex;
        align-items: center;
        gap: 0.5rem;
        padding: 8px 16px;
        cursor: pointer;
        transition: background-color 0.3s;

        &:hover {
          background-color: #dee7f4;
        }

        img {
          width: 20px;
          height: 20px;
        }

        p {
          color: #2b3467;
          margin: 0;
          font-size: 14px;
          font-weight: 500;
        }
      }
    }

    .locales-button-mobile {
      display: none;
      align-items: center;

      img {
        width: 25px;
        height: 25px;
        cursor: pointer;
      }

      img:nth-child(1) {
        margin-right: 10px;
      }
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
      display: none;
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: white;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      padding: 2rem;
      width: 70%;
      max-width: 400px;
      border-radius: 1rem;
      z-index: 20;
      opacity: 0;
      transition: opacity 0.3s ease-in-out;

      .locales-button {
        display: none;
      }
      .locales-button-mobile {
        display: flex;
        margin-top: 10px;
      }
    }

    .navigation.nav-active {
      display: flex;
      opacity: 1;
    }

    .hamburger {
      display: flex;
    }

    .overlay {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(0, 0, 0, 0.5);
      backdrop-filter: blur(5px);
      z-index: 10;
    }

    .nav-item {
      width: 100%;
    }
  }
}

@media (max-width: 1024px) {
  .header {
    padding: 2.2rem;
    &.scrolled {
      background-color: transparent;
      padding: 2.2rem;
    }
    .logo {
      &.scrolled {
        visibility: hidden;
      }
    }
  }
}
</style>
