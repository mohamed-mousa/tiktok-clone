<template>
  <nav
    id="TopNav"
    class="fixed bg-white z-30 flex items-center w-full border-b h-[61px]"
  >
    <div
      class="flex items-center justify-between w-full px-6 mx-auto"
      :class="route.fullPath === '/' ? 'max-w-[1150px]' : ''"
    >
      <div :class="route.fullPath === '/' ? 'w-[80%]' : 'lg:w-[20%] w-[70%]'">
        <nuxt-link to="/">
          <img
            src="~/assets/images/tiktok-logo.png"
            alt="tiktok-logo"
            width="115"
          />
        </nuxt-link>
      </div>

      <div
        class="hidden md:flex items-center bg-[#f1f1f2] p-1 rounded-full max-w-[380px] w-full"
      >
        <input
          type="text"
          class="w-full pl-3 my-2 bg-transparent placeholder-[#838383] text-[15px] focus:outline-none"
          placeholder="Search account"
        />

        <div class="px-3 py-1 flex items-center border-l border-l-gray-300">
          <Icon name="heroicons:magnifying-glass" color="#a1a2a7" />
        </div>
      </div>

      <div
        class="flex items-center justify-end gap-3 min-w-[275px] max-w-[320px] w-full"
      >
        <button
          class="flex items-center border rounded-sm px-3 py-[6px] hover:bg-gray-100"
        >
          <Icon name="mdi:plus" color="#000000" size="22" />
          <span class="px-2 font-medium text-[15px]">Upload</span>
        </button>

        <div v-if="!$userStore.id" class="flex items-center">
          <button
            @click="$generalStore.isLoginOpen = true"
            class="flex items-center bg-[#f02c56] text-white border rounded-md px-3 py-[6px]"
          >
            <span class="mx-4 font-medium text-[15px]">Log in</span>
          </button>

          <Icon name="mdi:dots-vertical" color="#161724" size="25" />
        </div>

        <div v-else class="flex items-center">
          <Icon
            name="carbon:send-alt"
            class="ml-1 mr-4"
            color="#161724"
            size="30"
          />
          <Icon
            name="bx:message-detail"
            class="mr-5"
            color="#161724"
            size="27"
          />

          <div class="relative">
            <button class="mt-1" @click="showMenu = !showMenu">
              <img
                src="~/assets/images/profile.jpg"
                alt="avatar"
                class="rounded-full"
                width="33"
                height="33"
              />
            </button>

            <div
              v-if="showMenu"
              id="PupupMenu"
              class="absolute bg-white rounded-lg py-1.5 w-[200px] shadow-xl border top-[43px] -right-[2]"
            >
              <nuxt-link
                to="/"
                @click="showMenu = false"
                class="flex items-center justify-start py-3 px-2 hover:bg-gray-100 cursor-pointer"
              >
                <Icon name="ph:user" size="20" />
                <span class="pl-2 font-semibold text-sm">Profile</span>
              </nuxt-link>
              <div
                class="flex items-center justify-start py-3 px-1.5 border-t hover:bg-gray-100 cursor-pointer"
              >
                <Icon name="ic:outline-login" size="20" />
                <span class="pl-2 font-semibold text-sm">Log out</span>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
const { $userStore, $generalStore } = useNuxtApp();
const route = useRoute();
const showMenu = ref(false);
</script>
