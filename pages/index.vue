<template>
  <p>
    This route causes no type checking error. It causes a runtime error:
<pre>No match for {"name":"this-route-does-not-exist","params":{}}</pre>
  </p>
  <NuxtLink :to="{ name: 'this-route-does-not-exist' }">
    This route does not exist
  </NuxtLink>

  <hr />

  <p>
    This route causes no type checking error, no runtime error. It causes runtime warning:
    <pre>
[Vue Router warn]: Discarded invalid param(s) "0", "1", "2", "3", "4", "5", "6", "7", "8", "9", "10", "11", "12", "13", "14", "15" when navigating. See https://github.com/vuejs/router/blob/main/packages/router/CHANGELOG.md#414-2022-08-22 for more details.
[Vue Router warn]: Discarded invalid param(s) "id" when navigating. See https://github.com/vuejs/router/blob/main/packages/router/CHANGELOG.md#414-2022-08-22 for more details.
    </pre>
  </p>

  <NuxtLink :to="{ name: 'detail', params: 'potato-casserole' }">
    This route has invalid params
  </NuxtLink>

  <hr />

  <NuxtLink :to="{ name: 'detail', params: { id: 'french-fries' } }">
    This route is valid
  </NuxtLink>
</template>
