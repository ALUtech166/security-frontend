<template>
  <div>

    <section class="lg:tw-pb-10 lg:tw-px-3 tw-p-4 tw-flex-col tw-gap-4 tw-mt-8">
      <div class="tw-w-full">
        <div class="tw-flex tw-flex-col tw-mb-6 tw-px-2 md:tw-px-6 tw-w-full">

          <div class="xl:tw-px-20">
            <p class="tw-text-black tw-text-lg tw-mt-2 tw-text-right tw-mb-4">
              Already Have an account ?
              <span><button @click="$router.push('/login')"
                  class="tw-group bg-hover tw-shadow-lg tw-rounded-lg tw-border-2 tw-relative tw-h-12 tw-mt-2 tw-cursor-pointer hover:tw-transform hover:tw-translate-x-2 hover:tw-transition-transform hover:tw-duration-300 tw-shadow-white hover:tw-shadow-2xl tw-w-48 tw-overflow-hidden tw-rounded-lg tw-text-lg tw-shadow-2xl">
                  <div
                    class="tw-absolute tw-inset-0 tw-w-full tw-border-2 tw-bg-gray-100 tw--transition-all tw-duration-[250ms] tw-ease-out group-hover:tw-w-full">
                  </div>
                  <span
                    class="tw-relative tw-inline-flex tw-items-center tw-gap-2 tw-text-black group-hover:tw-text-black">
                    Sign in

                  </span>
                </button></span>
            </p>
            <div
              class="tw-grid lg:tw-grid-cols-2 tw-gap-4 lg:tw-gap-0 tw-w-full tw-h-full tw-rounded-t-xl tw-shadow-2xl tw-shadow-gray-800">

              <div
                class=" tw-h-full tw-bg-white tw-block tw-cursor-pointer tw-rounded-xl tw-w-full tw-shadow-2xl tw-shadow-indigo-100">
                <img alt="Home"
                  src="https://img.freepik.com/free-vector/technology-background-concept_23-2148483796.jpg?w=740&t=st=1696442041~exp=1696442641~hmac=1eed6a71d9057dc6f5d831342f658a4f32fc618d877aeb0f10f23e176d97507a"
                  class="tw-h-full tw-w-full tw-object-cover tw-bg-opacity-60 tw-rounded-l-md tw-shadow-2xl" />
              </div>

              <div class="tw-bg-white  tw-block tw-cursor-pointer tw-w-full tw-shadow-2xl tw-shadow-indigo-100">
                <div class="tw-mx-10 tw-bg-white">
                  <h1 class="tw-mx-10 tw-text-4xl tw-font-extrabold tw-mt-4">
                    Welcome <br>
                    <span class="text-color">ALU Canvas</span>
                  </h1>
                  <p class="tw-mx-10 tw-text-black tw-text-md tw-mt-2">
                    Register your Account
                  </p>

                  <div class="tw-flex tw-gap-4 tw-mt-4 tw-mx-10">
                    <hr class="lg:tw-w-24 tw-w-12 tw-h-1 bg-color tw-my-1">
                    <hr class="lg:tw-w-24 tw-w-12 tw-h-1 tw-bg-gray-300 tw-my-1">

                  </div>
                </div>
                <form class="lg:tw-mt-0 lg:tw-px-8 tw-px-4 tw-py-4 lg:tw-py-8" @submit.prevent="registerUser">

                  <div class="tw-w-full tw-md:w-1/2">
                    <label class="tw-block tw-font-extrabold tw-mb-1" for="name">
                      Name
                    </label>

                    <input type="name" name="name" id="email" placeholder="John Doe" v-model="user.username"
                      class="tw-block tw-bg-gray-300 tw-placeholder-gray-300 tw-w-full  tw-text-black tw-shadow-xl tw-rounded-lg tw-outline-none  tw-mb-1 tw-p-3"
                      required>
                  </div>

                  <div class="tw-w-full tw-md:w-1/2 tw-mt-2">
                    <label class="tw-block tw-font-extrabold tw-mb-1" for="email">
                      Email Address
                    </label>

                    <input type="email" name="email" id="email" placeholder="email@example.com" v-model="user.email"
                      class="tw-block  tw-bg-gray-300 tw-placeholder-gray-300 tw-w-full  tw-text-black tw-shadow-xl tw-rounded-lg tw-outline-none  tw-mb-1 tw-p-3"
                      required>
                  </div>


                  <div class="tw-w-full tw-md:w-1/2">
                    <label class="tw-block tw-font-extrabold tw-mb-1" for="number">
                      Password
                    </label>
                  </div>
                  <password v-model="user.passwordConf"
                    class="tw-block tw-bg-gray-300 tw-placeholder-gray-300 tw-w-full  tw-text-black tw-shadow-xl tw-rounded-lg tw-outline-none  tw-mb-1 tw-p-3"
                    :toggle="true" />

                  <div class="tw-w-full tw-md:w-1/2">
                    <label class="tw-block tw-font-extrabold tw-mb-1" for="confirmPassword">
                      Confirm Password
                    </label>

                    <input type="password" name="confirmPassword" id="confirmPassword" placeholder="Confirm your Password"
                      v-model="user.password"
                      class="tw-block tw-bg-gray-300 tw-placeholder-gray-300 tw-w-full tw-text-black tw-shadow-xl tw-rounded-lg tw-outline-none tw-mb-1 tw-p-3"
                      required />

                    <!-- Display error message when passwords don't match -->
                    <div v-if="!passwordsMatch" class="tw-text-red-600">Passwords do not match.</div>
                  </div>
                  <div class="tw-w-full tw-md:w-1/2">
                    <label class="tw-block tw-font-extrabold tw-mb-1" for="number">
                      Role
                    </label>

                    <select v-model="user.role"
                      class="tw-block tw-bg-gray-300 tw-placeholder-gray-300 tw-w-full  tw-text-black tw-shadow-xl tw-rounded-lg tw-outline-none  tw-mb-1 tw-p-3">
                      <option value="student">Student</option>
                      <option value="facilitator">Facilitator</option>
                      <option value="teamlead">Team Lead</option>
                    </select>
                  </div>
                  <!-- Display registration error -->
                  <div v-if="registrationError" class="tw-text-red-600">{{ registrationError }}</div>

                  <button @click.prevent="registerUser"
                    class="tw-group bg-color tw-shadow-lg tw-rounded-lg tw-relative tw-h-12 tw-mt-4 tw-cursor-pointer hover:tw-transform hover:tw-translate-x-2 hover:tw-transition-transform hover:tw-duration-300 hover:tw-shadow-2xl-blue-600 hover:tw-shadow-2xl-lg tw-w-48 tw-overflow-hidden tw-rounded-lg tw-text-lg tw-shadow-2xl">
                    <div
                      class="tw-absolute tw-inset-0 tw-w-full bg-color tw--transition-all tw-duration-[250ms] tw-ease-out group-hover:tw-w-full">
                    </div>
                    <span
                      class="tw-relative tw-inline-flex tw-items-center tw-gap-2 tw-text-white group-hover:tw-text-white">
                      Sign Up

                    </span>
                  </button>
                </form>



              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>



<script>
import Password from '../components/Password.vue'
const swal = require('sweetalert2')

export default {
  components: { Password },
  data() {
    return {
      title: 'User Registration Page',
      user: {
        username: "",
        email: "",
        password: "",
        passwordConf: "",
        role: "student", // Default role
      },
      registrationError: null, // To store registration error messages
    }
  },

  computed: {

    passwordsMatch() {
      // Check if passwords match
      return this.user.password === this.user.passwordConf;
    },
    breadcrumbItems() {
      const items = [{
        text: 'Home',
        href: '/',
      },
      {
        text: 'Register',

      },

      ];

      return items.map((item) => ({
        ...item,
        disabled: !item.href,
      }));
    },
  },

  methods: {

    async registerUser() {
      console.log(this.password);
      // Check if passwords match before submitting the form
      if (!this.passwordsMatch) {
        this.registrationError = "Passwords do not match. Please re-enter.";
        return;
      }

      try {
        const response = await axios.post('/register', this.user);
        if (response.status === 201) {
          // Registration successful
          new swal({
            icon: 'success',
            title: 'Success',
            text: 'User is successfully registered!',
          });

          // You can optionally redirect the user to a login page
          this.$router.push('/login');
        } else {
          // Handle other response status codes if needed
          this.registrationError = "Registration failed. Please try again.";
        }
      } catch (error) {
        new swal({
      title: 'Error',
      text: 'An error occurred while Registration.',
      icon: 'error',
      confirmButtonText: 'Close',
    });

        this.registrationError = "Registration failed. Please try again.";
      }
    }

  },


}
</script>

<style scoped>
.bg-color {
  background-color: #C70039;
}

:hover.hover-bg {
  background-color: #C70039;
}


.text-color,
label {
  color: #C70039;
}


button {
  color: black
}
</style>
