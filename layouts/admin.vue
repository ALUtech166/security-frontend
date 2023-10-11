<template>
    <div class="tw-flex">
   <div class="">
     <!-- Sidebar menu -->
     <div class="tw-h-full tw-bg-gray-800 tw-text-white tw-pt-8 tw-px-4">
    <!-- Sidebar content -->
    <div class="tw-p-4">
      <h2 class="tw-text-2xl tw-font-semibold tw-mb-4">ALU
        Dashboard</h2>
      <!-- Your sidebar links can go here -->
      <img class="tw-rounded-full tw-shadow-lg tw-w-24 tw-mb-4" src="https://img.freepik.com/free-vector/illustration-businessman_53876-5856.jpg?w=740&t=st=1697046175~exp=1697046775~hmac=330e399bf2d05776a0c536414c76f499892cb4ec3baa89c724a7f98f1a171332" alt="">
      <ul>
        <li><NuxtLink to="/">Home</NuxtLink></li>
        <li><NuxtLink to="/courses">Courses</NuxtLink></li>
      </ul>
      <button @click="logout" class="tw-mt-8 tw-bg-red-500 tw-text-white tw-px-4 tw-py-2 tw-rounded-full hover:tw-bg-red-600">
        Logout
      </button>
    </div>
</div>
 
 
 
     <!-- Main content -->
     
   </div>
 
   <div class="tw-flex-1">
       <nuxt />
     </div>
   </div>
 </template>


  
  <script>
  export default {
    layout: "main",
    data() {
      return {};
    },
  };
  </script>
  
  <style scoped></style>
  