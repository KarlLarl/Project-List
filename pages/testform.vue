<template>
  <div class="flex-center">
        <div class="box-form">
            <FormInput/>
        </div>
  </div>
</template>

<script>

import FormInput from '~/components/FormInput'

export default {
  components: {
      FormInput
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Prompt:100,200,400,500,600,700&display=swap');

*{
    font-family: 'Prompt', sans-serif;
}
</style>
