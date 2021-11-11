<template>
  <div class="container">
      <h1 class="title">{{ $t('message') }}</h1>
      <LanguageInput />
      <!-- some code -->
  </div>
</template>

<script>
  import LanguageInput from '@/components/LanguageInput'

  export default {
    components: {
      LanguageInput
    }
  }
</script>