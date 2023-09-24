<template>
  <header>
    <div class="wrapper">
      <nav>
        <div class="logo">
        <p>FreeLanco</p><br/>
        </div>
        <div class="kanan">
        <RouterLink to="#home">Home</RouterLink>
        <RouterLink to="#konten">Konten</RouterLink>
        <RouterLink to="#meetteam">Meet Team</RouterLink>
        </div>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style scoped>

header {
  line-height: 1.5;
  /* max-height: 100vh; */
  display: block;
}

header .wrapper{
    display: block;
    /* place-items: flex-start; */
    flex-wrap: wrap;
  }

.logo {
  display: block;
  /* margin: 0 auto 2rem; */
  width: 50%;
  height: 40px;
}

.logo p{
  font-weight: 800;
}

nav {
  width: 100%;
  font-size: 20px;
  z-index: 1000;
  /* text-align: center; */
  /* text-align: left; */
  margin-left: -1rem;
  /* font-size: 1rem; */
  padding: 1rem 9rem 1rem 1rem;
  display: flex;
  position:fixed;
  background-color: white;

}

nav a.router-link-exact-active {
  color: #5D5FEF;
}

nav a.router-link-exact-active:hover {
  color: #5D5FEF;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
}

nav a:first-of-type {
  border: 0;
}

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;
    padding: 1rem 0;
    margin-top: 1rem;
  }
} */
</style>

<script>
export default {
  created() {
    // Tangani navigasi ke anchor saat komponen dibuat
    this.handleAnchorNavigation();
  },
  watch: {
    $route(to) {
      // Tangani navigasi ke anchor saat rute berubah
      this.handleAnchorNavigation();
    },
  },
  methods: {
    handleAnchorNavigation() {
      const targetHash = this.$route.hash;
      if (targetHash) {
        const targetElement = document.querySelector(targetHash);
        if (targetElement) {
          targetElement.scrollIntoView({ behavior: 'smooth' });
        }
      }
    },
  },
};
</script>
