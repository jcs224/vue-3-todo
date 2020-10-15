<template>
  <footer class="relative flex flex-wrap items-center justify-between px-2 py-3 navbar-expand-lg bg-gray-700 mt-3">
    <div class="container px-4 mx-auto flex flex-wrap items-center justify-between">
      <div class="w-full relative flex justify-between lg:w-auto  px-4 lg:static lg:block lg:justify-start">
        <a class="text-sm font-bold leading-relaxed inline-block mr-4 py-2 whitespace-no-wrap uppercase text-white" href="/">
          <font-awesome-icon :icon="logoIcon" /> AmazeTodos
        </a>
      </div>
    </div>
  </footer>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faCheckSquare } from '@fortawesome/free-solid-svg-icons'
export default {
  name: "footer",
  data() {
    return {
      logoIcon: faCheckSquare
    }
  },
  methods: {
    toggleNavbar: function(){
      this.showMenu = !this.showMenu;
    }
  },

  components: {
    FontAwesomeIcon
  }
}
</script>