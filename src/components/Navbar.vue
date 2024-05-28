<template>
  <div>
    <Login v-if="isModal" @close="closeModal" />
    <div class="container">
      <div
        class="flex justify-between border border-x-white border-b-green-700 py-8 max-sm:w-[380px]"
      >
        <div class="max-sm:hidden">
          <img src="../assets/Group.png" alt="Logo" />
        </div>
        <div class="flex gap-12 max-sm:hidden">
          <a href="#">Home</a>
          <a href="#">Shop</a>
          <a href="#">Plant Care</a>
          <a href="#">Blogs</a>
        </div>
        <div class="flex items-center gap-4 relative">
          <div class="flex justify-between items-center relative gap-2">
            <input
              type="text"
              class="outline-none border border-black/10 rounded-md h-[50px] w-[330px] pl-12 md:hidden"
              placeholder="Find your plants"
            />
            <img
              src="../assets/search.svg"
              alt="Search Icon"
              class="h-[32px] absolute ml-2"
            />
            <div
              class="flex items-center gap-2 border rounded-md bg-green-600 text-white py-3 px-5 cursor-pointer md:hidden"
              @click="toggleModal"
            >
              <img src="../assets/login.svg" alt="Login Icon" />
            </div>
          </div>
            <img src="../assets/search.svg" alt="Search Icon" class="h-[32px] max-sm:hidden" />

          <div
            class="w-[12px] h-[12px] rounded-full bg-green-700 flex items-center justify-center absolute ml-[65px] mb-7 max-sm:hidden"
          >
            <span class="text-white text-[10px]">6</span>
          </div>
          <img
            src="../assets/cart.svg"
            alt="Cart Icon"
            class="h-[32px] max-sm:hidden"
          />
          <div
            class="flex items-center gap-2 border rounded-md bg-green-600 text-white py-3 px-5 cursor-pointer max-sm:hidden"
            @click="toggleModal"
          >
            <img src="../assets/login.svg" alt="Login Icon" />

            <button class="text-sm">Login</button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Login from "../components/Login.vue";

export default {
  name: "ParentComponent",
  components: {
    Login,
  },
  data() {
    return {
      isModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.isModal = !this.isModal;
    },
    closeModal() {
      this.isModal = false;
    },
  },
};
document.addEventListener("DOMContentLoaded", function () {
  const password = document.getElementById("password");
  const togglePassword = document.getElementById("togglePassword");

  togglePassword.addEventListener("click", function () {
    // Toggle the type attribute
    const type =
      password.getAttribute("type") === "password" ? "text" : "password";
    password.setAttribute("type", type);

    // Toggle the eye icon (optional, you can use different icons)
    this.textContent = type === "password" ? "👁️" : "🙈";
  });
});
</script>

<style lang="css" scoped>
/* Add your styles here */
</style>
