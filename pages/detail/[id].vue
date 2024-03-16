<script setup type="typescript">
definePageMeta({ name: 'detail' })

const route = useRoute('detail')

// On CLI:
// [nitro] [unhandledRejection] TypeError: Cannot read properties of undefined (reading 'params')
// In browser:
// `500 - string is not defined`.
//
// No error is flagged by typecheck.
const derivedId = computed<string>(() => {
  try {
    return route.params.thisParamIsInvalid ?? ''
  } catch (error) {
    return error.message
  }
})
</script>

<template>
  <p>Test file</p>
  <p>id: {{ route.params.id }}</p>
  <p>derivedId: {{ derivedId }}</p>
</template>
