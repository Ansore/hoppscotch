<template>
  <div class="collection">
    <h2 class="heading">
      <SmartIcon name="folder" class="svg-icons" />
      {{ collection.name || $t("state.none") }}
    </h2>
    <span
      v-for="(folder, index) in collection.folders"
      :key="`folder-${index}`"
      class="folder"
    >
      <DocsFolder :folder="folder" />
    </span>
    <div
      v-for="(request, index) in collection.requests"
      :key="`request-${index}`"
    >
      <DocsRequest :request="request" />
    </div>
  </div>
</template>

<script>
import { defineComponent } from "@nuxtjs/composition-api"

export default defineComponent({
  props: {
    collection: { type: Object, default: () => {} },
  },
})
</script>

<style scoped lang="scss">
.collection {
  @apply flex flex-col flex-1;
  @apply justify-center;
  @apply p-4;

  .material-icons {
    @apply mr-4;
  }
}
</style>
