<template>
  <div class="text-center text-[28px] mb-4 font-bold">Sign up</div>

  <div class="px-6 pb-2">
    <TextInput
      inputType="text"
      :autoFocus="true"
      error=""
      placeholder="Name"
      v-model:input="email"
    />
  </div>
  <div class="px-6 pb-2">
    <TextInput
      inputType="email"
      error=""
      placeholder="Email address"
      v-model:input="email"
    />
  </div>
  <div class="px-6 pb-2">
    <TextInput
      inputType="password"
      placeholder="Password"
      v-model:input="password"
    />
  </div>
  <div class="px-6 pb-2">
    <TextInput
      inputType="password"
      placeholder="Confirm password"
      v-model:input="confirmPassword"
    />
  </div>

  <div class="px-6 pb-2 mt-6">
    <button
      :disabled="!email || !password || !name || !confirmPassword"
      :class="
        !email || !password || !name || !confirmPassword
          ? 'bg-gray-200'
          : 'bg-[#f02c56]'
      "
      class="w-full text-[17px] font-semibold text-white py-3 rounded-sm"
      @click="register()"
    >
      Sign up
    </button>
  </div>
</template>

<script setup>
let email = ref(null);
let password = ref(null);
let name = ref(null);
let confirmPassword = ref(null);
let errors = ref(null);
</script>
