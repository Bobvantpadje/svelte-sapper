
<script lang="ts">
  import { GoogleAuth } from '@beyonk/svelte-social-auth';

  const YOUR_CLIENT_ID =
    "406460855468-59gcn6gkbruheij8gnosc6845lsil0a6.apps.googleusercontent.com";
  const YOUR_CLIENT_SECRET = "2D3V32nz3k4wBLMWxnvUSfDN";
  const YOUR_REDIRECT_URL = "http://localhost:3000";
  let email: string = "";
</script>

<div class="w-full min-h-screen flex">
  <div class="w-1/2 bg-purple-900"></div>
  <div class="w-1/2 flex flex-col align-middel justify-center text-center">
    <h1>Welcome to passionate people</h1>
    <h2>Please log in!</h2>
    <input bind:value="{email}" placeholder="enter email" />
    <button class="bg-red-400">login</button>
    <GoogleAuth clientId="406460855468-59gcn6gkbruheij8gnosc6845lsil0a6.apps.googleusercontent.com" on:auth-success={e => console.dir(e.detail.user)} />
  </div>
</div>
