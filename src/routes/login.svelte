<script lang="ts">
  import GoogleAuth from "../components/GoogleAuth.svelte";
  import { goto } from "@sapper/app";
</script>

<div class="w-full min-h-screen flex bg-purple-900 justify-center">
  <div class="w-1/2 hidden lg:block"></div>
  <div class="w-10/12 lg:w-1/2 lg:bg-white flex justify-center items-center">
    <div
      class="flex flex-col align-middel justify-center text-center bg-white p-8
      rounded-lg max-w-sm"
    >
      <img src="logo-black-text.e1c73a1.svg" alt="logo" />
      <span class="mt-6 font-bold">Welcome to passionate people</span>
      <span class="mt-4">Please login using your google account!</span>
      <div class="mt-4">
        <GoogleAuth
          onSuccess="{() => {
            goto('/');
          }}"
        />
      </div>
    </div>
  </div>
</div>
