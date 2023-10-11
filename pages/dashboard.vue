<template>
  <div class="">

  <section class="tw-py-6 tw-px-4">
    <h2 class="tw-text-2xl tw-font-semibold tw-mb-4 text-color">ALU Canvas Dashboard</h2>

    <div class="tw-bg-gray-300 tw-shadow-lg tw-rounded-lg tw-p-8">
      <h2 class="tw-text-2xl tw-font-semibold tw-mb-4 text-color">Enrolled Courses</h2>
      <p>You have not enrolled in any course yet.</p>
    </div>

        <div class="tw-mt-4 tw-mb-4 tw-bg-gray-300 tw-shadow-lg tw-rounded-lg tw-p-8">
          <h2 class="tw-text-2xl tw-font-semibold tw-mb-4 text-color">Browse available courses</h2>

          <div class="tw-mt-3 tw-grid tw-grid-cols-1 tw-gap-3 sm:tw-grid-cols-1 lg:tw-grid-cols-3">
          
            <div class="tw-bg-white tw-cursor-pointer tw-shadow-lg tw-rounded-lg">
              <div class="">
                <img class="tw-shadow-lg" src="https://img.freepik.com/free-photo/standard-quality-control-collage-concept_23-2149595831.jpg?w=740&t=st=1697046443~exp=1697047043~hmac=9c118bd6f340c1892c59b5960aa2182923c951f7a33041cdb482cebe0f16a631" alt="">
                <h3 class="tw-mt-2 tw-px-2 tw-text-left tw-text-xl tw-font-bold text-color">
                  Security
                </h3>
                <div class="tw-px-2 tw-mt-2 tw-mb-2 tw-text-left tw-text-sm tw-text-gray-600">
                  <p class="tw-mt-1">Year 2024</p>
                  <p class="">Mr Simone</p>
                </div>
              </div>
            </div>

            <div class="tw-bg-white tw-cursor-pointer tw-shadow-lg tw-rounded-lg">
              <div class="">
                <img class="tw-rounded-lg" src="https://img.freepik.com/premium-photo/professional-accountant-working-wooden-desk-office_495423-65228.jpg?w=740" alt="">
                <h3 class="tw-mt-2 tw-px-2 tw-text-left tw-text-xl tw-font-bold text-color">
                  Computer Research
                </h3>
                <div class="tw-px-2 tw-mt-2 tw-mb-2 tw-text-left tw-text-sm tw-text-gray-600">
                  <p class="tw-mt-1">Year 2024</p>
                  <p class="">Mr Isaac</p>
                </div>
              </div>
            </div>

            
          </div>
        </div>
        </section>
  </div>
</template>

<script>
export default {
  layout: 'admin',
  methods: {
    logout() {
      // Implement your logout logic here
    },
  },
};
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