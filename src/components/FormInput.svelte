<script>
  export let id;
  export let label;
  export let value = '';
  export let inputOptions = {};

  $: labelClassName = `${value?.length ? 'shrink' : ''} form-input-label`;
</script>

<div class="form-group">
  <input {id} class="form-input" bind:value={value} {...inputOptions} />
  {#if label}
    <label for={id} class={labelClassName}>{label}</label>
  {/if}
</div>

<style lang="scss">
  $sub-color: grey;
  $main-color: black;

  @mixin shrinkLabel {
    top: -14px;
    font-size: 12px;
    color: $main-color;
  }

  .form-group {
    position: relative;
    margin: 45px 0;

    .form-input {
      background: none;
      background-color: white;
      color: $sub-color;
      font-size: 18px;
      padding: 10px 10px 10px 5px;
      display: block;
      width: 100%;
      border: none;
      border-radius: 0;
      border-bottom: 1px solid $sub-color;
      margin: 25px 0;

      &:focus {
        outline: none;
      }

      &:focus ~ .form-input-label {
        @include shrinkLabel();
      }
    }

    input[type='password'] {
      letter-spacing: 0.3em;
    }

    .form-input-label {
      color: $sub-color;
      font-size: 16px;
      font-weight: normal;
      position: absolute;
      pointer-events: none;
      left: 5px;
      top: 10px;
      transition: 300ms ease all;

      &.shrink {
        @include shrinkLabel();
      }
    }
  }
</style>
