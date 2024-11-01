<template>
  <wwLayout
    class="ww-flexbox"
    path="children"
    :direction="content.direction"
    :disable-edit="isFixed"
    ww-responsive="wwLayout"
    :tag="tag"
    v-bind="properties"
    :class="{ '-link': hasLink && !isEditing }"
  >
    <template #header>
      <wwBackgroundVideo
        v-if="backgroundVideo"
        :video="backgroundVideo"
      ></wwBackgroundVideo>
    </template>
    <template #default="{ item, index, itemStyle }">
      <wwElement
        :key="content.children[index][content.propKey] || index"
        v-bind="item"
        :extra-style="itemStyle"
        class="ww-flexbox__object"
        :ww-responsive="`wwobject-${index}`"
        :data-ww-flexbox-index="index"
        @click="onElementClick"
      ></wwElement>
    </template>
  </wwLayout>
</template>
<script>
export default {
  props: {
    content: { type: Object, required: true },
  },
  computed: {},
  mounted() {},
  methods: {},
};
</script>
