<template>
   <Navbar></Navbar>
	  <router-view></router-view>
</template>

<script>
    export default {
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
