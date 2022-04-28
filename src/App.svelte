<script>
  import { Router, Link, Route } from 'svelte-routing';
  import Home from './pages/Home.svelte';
  import About from './pages/About.svelte';

  export let url = '';
</script>

<Router {url}>
  <nav>
    <Link to="/">Home</Link>
    <Link to="about">About</Link>
  </nav>
  <div>
    <Route path="about" component={About} />
    <Route path="/"><Home /></Route>
  </div>
</Router>

<style>
  :root {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
</style>
