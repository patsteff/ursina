<script setup>

/* const mobileMenu = document.querySelector('.mobile-menu');
const nav = document.querySelector('nav');
const hamburger = document.querySelector('.hamburger');
const menuItem = document.querySelectorAll('.mobile-menu-item');
console.log(menuItem)

hamburger.addEventListener('click', function () {
  this.classList.toggle('is-active');
  mobileMenu.classList.toggle('is-active');

})

menuItem.forEach(item => {
  item.addEventListener('click', () => {
    console.log("clicked menu item")
    mobileMenu.classList.toggle('is-active');
    hamburger.classList.toggle('is-active');
  })
}); */

</script>

<template>
  <nav>
    <div class="container">
      <!-- primary nav -->
      <div class="menu">
        <a href="#intro" class="decoration-none">Aktivitäten</a>
        <a href="#events" class="decoration-none">Mitmachen</a>
        <a href="#support" class="decoration-none">Unterstützen</a>
      </div>
      <!-- mobile menu -->
      <button class="hamburger">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>

    <div class="mobile-menu" id="mobile-menu">
      <a href="#about" class="mobile-menu-item decoration-none">Aktivitäten</a>
      <a href="#events" class="mobile-menu-item decoration-none">Mitmachen</a>
      <a href="#support" class="mobile-menu-item decoration-none">Unterstützen</a>

    </div>
  </nav>
</template>

<style scoped>
nav {
  top: 0;
  left: 0;
  right: 0;
  position: fixed;
  z-index: 50;
  padding: 16px 32px;
  border: 2px solid red;
}

.menu a {
  margin: 0 16px;
  transform: 0.4s;
  padding: 8px 16px;
  border-radius: 99px;
}

.menu a.is-active,
.menu a:hover {
  background-color: var(--darkerpink);
}

.hamburger {
  display: block;
  position: relative;
  z-index: 1;
  user-select: none;
  appearance: none;
  border: none;
  outline: none;
  background: none;
  cursor: pointer;
}

.hamburger span {
  display: block;
  width: 33px;
  height: 4px;
  margin-bottom: 5px;
  position: relative;
  background-color: black;
  border-radius: 6px;
  z-index: 1;
  transform-origin: 0 0;
  transition: 0.4s;
}

.hamburger:hover span:nth-child(2) {
  transform: translateX(5px);
  background-color: var(--green);
}

.hamburger.is-active span:nth-child(1) {
  transform: translate(0px, -2px) rotate(45deg);
}

.hamburger.is-active span:nth-child(3) {
  transform: translate(-3px, 3px) rotate(-45deg);
}

.hamburger.is-active span:nth-child(2) {
  opacity: 0;
}

.hamburger.is-active span {
  background-color: black;
}

.menu {
  display: none;
  flex: 1 1 0%;
  justify-content: flex-start;
  /* offset margin from below */
  margin: 0 -16px;
}

.menu a {
  font-size: 16px;
  color: black;
}

.mobile-menu {
  display: none;
}

.mobile-menu.is-active {
  display: flex;
  flex-direction: column;
  margin-top: 20px;
  margin-bottom: -10px;
}

.mobile-menu.is-active a {
  margin-bottom: 10px;
}

@media screen and (min-width: 1000px) {
  .hamburger {
    display: none;
  }

  .menu {
    display: flex;
  }
}
</style>
