<script lang="ts">
  import { GoogleAuth } from "@beyonk/svelte-social-auth";
  // TODO: see if it is possible to pass the event so we don't have to create a new onSuccess function: https://svelte.dev/tutorial/event-forwarding
  export let onSuccess = (e: any) => {
    console.log("Pass your success function here");
  };
  export const onError = () => {};
</script>

<!-- const YOUR_CLIENT_ID =
    "406460855468-59gcn6gkbruheij8gnosc6845lsil0a6.apps.googleusercontent.com";
  const YOUR_CLIENT_SECRET = "2D3V32nz3k4wBLMWxnvUSfDN";
  const YOUR_REDIRECT_URL = "http://localhost:3000"; -->
<GoogleAuth
  clientId="406460855468-59gcn6gkbruheij8gnosc6845lsil0a6.apps.googleusercontent.com"
  on:auth-success="{onSuccess}"
/>
