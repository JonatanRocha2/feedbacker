<template>
  <custom-header
    @create-account="handlerCreateAccount"
    @login="handlerLogin"
  />
  <contact />
  <div class="flex justify-center py-10 bg-brand-gray">
    <p class="font-madium text-center text-gray-800">feedbacker © 2022</p>
  </div>
</template>

<script>

import CustomHeader from './CustomHeader.vue'
import Contact from './Contact.vue'
import { useRoute } from 'vue-router'
import { onMounted } from '@vue/runtime-core'

export default {
  components: { CustomHeader, Contact },
  setup () {
    const router = useRoute()

    onMounted(() => {
      const token = window.localStorage.getItem('token')
      if (token) {
        router.push({
          name: 'Feedbacks'
        })
      }
    })
    function handlerLogin () {
    }
    function handlerAccountCreate () {
    }

    return {
      handlerLogin,
      handlerAccountCreate
    }
  }
}
</script>