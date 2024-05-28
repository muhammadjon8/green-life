<template>
  <div>
    <div
      @click="closeModal"
      class="fixed bg-black/60 top-0 left-0 w-full h-screen z-10"
    ></div>
    <div
      class="fixed bg-white top-1/2 left-1/2 rounded -translate-x-1/2 -translate-y-1/2 w-[500px] p-5 z-20"
    >
      <div class="flex justify-end">
        <button @click="closeModal">X</button>
      </div>
      <div class="flex justify-center divide-x-2 divide-green-600">
        <button
          @click="content = 'login'"
          class="py-1 px-5"
          :class="{
            ' text-green-600 font-bold text-[18px]': content === 'login',
            'text-black': content !== 'login',
          }"
        >
          Login
        </button>
        <button
          @click="content = 'register'"
          class="py-1 px-5"
          :class="{
            'text-green-600 font-bold text-[18px]': content === 'register',
            'text-black': content !== 'register',
          }"
        >
          Register
        </button>
      </div>
      <div v-if="content == 'login'">
        <div class="px-[50px] flex flex-col items-center gap-3 py-8">
          <h3 class="py-3">Enter your username and password to login</h3>
          <div>
            <input
              type="email"
              placeholder="almamnun_uxui@outlook.com"
              class="w-[300px] px-3 h-[40px] border rounded border-black/10 outline-none focus:border-green-600"
            />
          </div>
          <div class="flex relative flex-col">
            <input
              :type="showPassword ? 'text' : 'password'"
              class="w-[300px] px-3 h-[40px] border rounded border-black/10 outline-none pr-8 focus:border-green-600"
            />
            <img
              v-if="showPassword"
              @click="showPassword1"
              src="../assets/hidden.svg"
              alt=""
              class="absolute right-2 top-3"
            />
            <img
              v-else
              @click="showPassword1"
              src="../assets/visible.svg"
              alt=""
              class="absolute right-2 top-3"
            />
            <button class="py-1 px-5 right-0">Forgot Password?</button>
          </div>
          <h3 class="text-gray-400 py-3">Or login With</h3>
          <button
            class="py-1 px-5 w-[300px] h-[40px] bg-green-600 text-white rounded"
          >
            Login
          </button>
          <button
            class="py-1 px-5 w-[300px] h-[40px] rounded border border-black/10 flex items-center gap-2 justify-center"
          >
            <img src="../assets/google.svg" alt="" />Login with Google
          </button>
          <button
            class="py-1 px-5 w-[300px] h-[40px] rounded border border-black/10 flex items-center gap-2 justify-center"
          >
            <img src="../assets/facebook.svg" alt="" />Login with Facebook
          </button>
        </div>
      </div>
      <div v-if="content == 'register'">
        <div class="px-[50px] flex flex-col items-center gap-3 py-8">
          <h3 class="py-3">Enter your username and password to register</h3>
          <div>
            <input
              type="text"
              placeholder="Username"
              class="w-[300px] px-3 h-[40px] border rounded border-black/10 outline-none focus:border-green-600"
            />
          </div>
          <div>
            <input
              type="email"
              placeholder="Enter your email address"
              class="w-[300px] px-3 h-[40px] border rounded border-black/10 outline-none focus:border-green-600"
            />
          </div>
          <div class="flex relative flex-col">
            <input
              type="password"
              placeholder="Password"
              class="w-[300px] px-3 h-[40px] border rounded border-black/10 outline-none pr-8 focus:border-green-600"
            />
            <img
              src="../assets/hidden.svg"
              alt=""
              class="absolute right-2 top-3"
            />
          </div>
          <div>
            <input
              type="password"
              placeholder="Confirm password"
              class="w-[300px] px-3 h-[40px] border rounded border-black/10 outline-none focus:border-green-600"
            />
          </div>
          <button
            class="py-1 px-5 w-[300px] h-[40px] bg-green-600 text-white rounded"
          >
            Register
          </button>
          <h3 class="text-gray-400 py-3">Or register With</h3>
          <button
            class="py-1 px-5 w-[300px] h-[40px] rounded border border-black/10 flex items-center gap-2 justify-center"
          >
            <img src="../assets/google.svg" alt="" />Login with Google
          </button>
          <button
            class="py-1 px-5 w-[300px] h-[40px] rounded border border-black/10 flex items-center gap-2 justify-center"
          >
            <img src="../assets/facebook.svg" alt="" />Login with Facebook
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      content: "login",
      showPassword: false,
    };
  },
  methods: {
    closeModal() {
      this.$emit("close");
    },
    showPassword1() {
      this.showPassword = !this.showPassword;
    },
  },
};
</script>

<style lang="css" scoped></style>
