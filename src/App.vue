<script >
import Navbar from "./components/Navbar.vue";
import MainPage from "./components/MainPage.vue";
import Products from "./components/Products.vue";
import Categories from "./components/Categories.vue";
import Specials from "./components/Specials.vue";
import BlogPost from "./components/BlogPost.vue";
import NewsLetter from "./components/NewsLetter.vue";
import Login from "./components/Login.vue";

export default {
  components: {
    Navbar,
    MainPage,
    Products,
    Categories,
    Specials,
    BlogPost,
    NewsLetter,
    Login,
  },
}
</script>

<template>
  
  <div>
    <Navbar class="pb-9" />
    <MainPage />
    <div class="grid md:grid-cols-4 max-sm:grid-cols-2 container gap-[50px]">
      <Categories class="col-span-1 max-sm:hidden" />
      <Products class="col-span-3 max-sm:col-span-2" />
    </div>
    <Specials class="py-10" />
    <BlogPost class="py-10" />
    <NewsLetter class="py-10" />
  </div>
</template>

<style scoped></style>
