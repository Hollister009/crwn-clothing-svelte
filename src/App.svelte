<script>
  import { Router, Route } from 'svelte-routing';
  import Home from './pages/Home.svelte';
  import About from './pages/About.svelte';
  import Navigation from './components/Navigation.svelte';
  import './index.scss';

  export let url = '';
</script>

<Router {url}>
  <Navigation />
  <div>
    <Route path="about" component={About} />
    <Route path="/"><Home /></Route>
  </div>
</Router>

