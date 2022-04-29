<script>
  import { signInWithGooglePopup, createUserDocumentFromAuth } from '../firebase/firebase.utils';
  import SignUpForm from '../components/SignUpForm.svelte';

  async function logGoogleUser() {
    const { user } = await signInWithGooglePopup();
    await createUserDocumentFromAuth(user);
  }
</script>

<main>
  <h2>Sign In</h2>
  <button type="button" on:click={logGoogleUser}> Sign In with Google Popup </button>
  <SignUpForm />
</main>
