<script>
  import FormInput from './FormInput.svelte';

  let displayName = '';
  let email = '';
  let password = '';
  let confirmPassword = '';

  $: formInputFields = [
    {
      id: 'displayName',
      label: 'Display Name',
      value: displayName,
      inputOptions: {
        type: 'text',
        name: 'displayName',
        required: true,
      },
    },
    {
      id: 'email',
      label: 'Email',
      value: email,
      inputOptions: { type: 'text', name: 'email', required: true },
    },
    {
      id: 'password',
      label: 'Password',
      value: password,
      inputOptions: { type: 'password', name: 'password', required: true },
    },
    {
      id: 'confirmPassword',
      label: 'ConfirmPassword',
      value: confirmPassword,
      inputOptions: { type: 'password', name: 'confirmPassword', required: true },
    },
  ];

  async function handleSubmit(evt) {
    evt.preventDefault();
    console.log(evt);
  }
</script>

<div class="sign-up-container">
  <h2>Sign up with your email and password</h2>
  <form action="POST" on:submit={handleSubmit}>
    {#each formInputFields as inputProps (inputProps.id)}
      <FormInput {...inputProps} />
    {/each}
    <button type="submit">Sign Up</button>
  </form>
</div>

<style lang="scss">
  .sign-up-container {
    display: flex;
    flex-direction: column;
    width: 380px;

    h2 {
      margin: 10px 0;
    }
  }
</style>
