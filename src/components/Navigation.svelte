<script>
  import { link } from 'svelte-routing';
  import logo from '../assets/crown.svg';
</script>

<nav>
  <a class="logo-container" href="/" use:link>
    <img class="logo" src={logo} alt="Logo" />
  </a>
  <div class="nav-links-container">
    <a class="nav-link" href="/shop" use:link>SHOP</a>
    <a class="nav-link" href="/sign-in" use:link>SIGN IN</a>
  </div>
</nav>

<style lang="scss">
  nav {
    height: 70px;
    width: 100%;
    display: flex;
    justify-content: space-between;
    margin-bottom: 25px;

    .logo-container {
      height: 100%;
      width: 70px;
      padding: 25px;
    }

    .nav-links-container {
      width: 50%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: flex-end;

      .nav-link {
        padding: 10px 15px;
        cursor: pointer;
      }
    }
  }
</style>
