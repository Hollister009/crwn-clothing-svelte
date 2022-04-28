<script>
  import { Router, Route } from 'svelte-routing';
  import Home from './pages/Home.svelte';
  import Shop from './pages/Shop.svelte';
  import SignIn from './pages/SignIn.svelte';
  import Navigation from './components/Navigation.svelte';
  import './index.scss';

  export let url = '';
</script>

<Router {url}>
  <Navigation />
  <div>
    <Route path="/"><Home /></Route>
    <Route path="shop" component={Shop} />
    <Route path="sign-in" component={SignIn} />
  </div>
</Router>

