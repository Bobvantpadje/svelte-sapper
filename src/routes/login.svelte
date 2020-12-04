<script lang="ts">
  import { GoogleAuth } from "@beyonk/svelte-social-auth";
  import Index from "./index.svelte";

  const YOUR_CLIENT_ID =
    "406460855468-59gcn6gkbruheij8gnosc6845lsil0a6.apps.googleusercontent.com";
  const YOUR_CLIENT_SECRET = "2D3V32nz3k4wBLMWxnvUSfDN";
  const YOUR_REDIRECT_URL = "http://localhost:3000";
  let email: string = "";
</script>

<div class="w-full min-h-screen flex bg-purple-900 justify-center">
  <div class="w-1/2 hidden lg:block"></div>
  <div class="w-10/12 lg:w-1/2 lg:bg-white flex justify-center items-center">
    <div
      class="flex flex-col align-middel justify-center text-center bg-white p-8
      rounded-lg max-w-sm"
    >
      <img src="logo-black-text.e1c73a1.svg" alt="logo" />
      <h1>Welcome to passionate people</h1>
      <h2>Please log in!</h2>
      <input bind:value="{email}" placeholder="enter email" />
      <button class="bg-red-400">login</button>
      <GoogleAuth
        clientId="406460855468-59gcn6gkbruheij8gnosc6845lsil0a6.apps.googleusercontent.com"
        on:auth-success="{(e) => console.dir(e.detail.user)}"
      />
    </div>
  </div>
</div>
