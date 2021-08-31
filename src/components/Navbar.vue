<template>
  <nav
    class=" flex justify-between p-3 border-4 bg-white border-gray-800 mt-2 shadow-2xl "
    v-if="user"
  >
    <div>
      <p class="font-semibold text-2xl">Halo {{ user.displayName }}</p>
      <p class="email font-medium">Currently logged in as {{ user.email }}</p>
    </div>
    <div class="flex items-center">
      <div class=" font-semibold mx-3 max-w-lg py-2 px-6 focus:outline-none focus:bg-yellow-800 rounded border-2 border-gray-700 text-lg shadow-lg transform hover:-translate-y-1 ease-in-out duration-700 ">
        <router-link :to="{ name: 'addProject' }">Add new Project</router-link>
      </div>
      <div class=" font-semibold mx-3 max-w-lg py-2 px-6 focus:outline-none focus:bg-yellow-800 rounded border-2 border-gray-700 text-lg shadow-lg transform hover:-translate-y-1 ease-in-out duration-700 ">
        <router-link :to="{ name: 'adddDonationID', params: { id: user.email } }">
          Donasi
        </router-link>
        Donasi
        class="p-3 border-4 rounded bg-white border-gray-700 mt-2 shadow-2xl"
        v-if="user"
        >
        <div class="w-full">
          <div class="flex justify-between items-baseline">
            <p class="font-bold text-xl">Halo {{ user.displayName }}</p>
            <p class="email font-medium text-gray-500">
              logged in as {{ user.email }}
            </p>
          </div>
          <div class="w-full flex items-center justify-between mt-3">
            <div class="flex flex-1 max-w-md">
              <div class="
              font-semibold
              w-1/2
              py-2
              px-3
              mx-2
              text-center
              focus:outline-none
              focus:bg-yellow-800
              bg-yellow-500
              rounded
              border-2 border-gray-700
              text-lg
              shadow-lg
              transform
              hover:-translate-y-1
              ease-in-out
              duration-300
            ">
                <router-link :to="{ name: 'adddDonation' }">Donasi</router-link>
              </div>
              <div class="
              py-2
              px-3
              mx-2
              text-center
              focus:outline-none
              focus:bg-yellow-800
              rounded
              border-2 border-gray-700
              text-md
              font-bold
              shadow-lg
              transform
              hover:-translate-y-1
              ease-in-out
              duration-300
            ">
                <router-link :to="{ name: 'addProject' }">Add new</router-link>
              </div>
            </div>

            <button
              @click="handleClick"
              class=" mx-3 max-w-lg py-2 px-6 focus:outline-none focus:bg-yellow-800 rounded bg-yellow-600 text-lg font-semibold shadow-lg transform hover:-translate-y-1 ease-in-out duration-700 "
            >
              Logout
            </button>
            <button
              @click="handleClick"
              class="
            py-2
            px-3
            mx-2
            text-center
            focus:outline-none
            focus:bg-yellow-800
            hover:bg-red-600
            hover:text-white
            rounded
            border-2 border-gray-500
            text-lg
            font-semibold
            shadow
            transform
            hover:-translate-y-1
            ease-in-out
            duration-300
          "
            >
              Logout
            </button>
          </div>
        </div>
  </nav>
</template>

<script>
import useLogout from "../composables/useLogout";
import getUser from "../composables/getUser";

export default {
  setup() {
    const { logout, error } = useLogout();
    const { user } = getUser();

    const handleClick = async () => {
      await logout();
      if (!error.value) {
        console.log("user logged out");
      }
    };

    // const rekDonasi = async () => {
    //   console.log('rekclisk')
    //   // await logout()
    //   // if (!error.value) {
    //   //   console.log('user logged out')
    //   // }
    // }

    return { handleClick, user };
  },
  methods: {
    rekDonasi(user) {
      console.log(user.displayName);
      console.log("aaa");
    },
    return { handleClick, user };
  },
};
</script>

<style>
</style>