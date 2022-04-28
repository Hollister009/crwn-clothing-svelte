<script>
  import Category from './Category.svelte';
  import { CATEGORIES } from '../constants';
</script>

<div class="categories-container">
  {#each CATEGORIES as { title, imageUrl }}
    <Category {title} {imageUrl} />
  {/each}
</div>

<style>
  .categories-container {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
  }
</style>
