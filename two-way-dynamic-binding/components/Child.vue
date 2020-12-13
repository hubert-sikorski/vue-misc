<template>
  <div class="g-checkbox-block">
    <input
      type="checkbox"
      @change="$emit('change', checked)"
      v-model="checked"
      :disabled="disabled"
    />
    <p v-if="!(!!link)">{{ text }}</p>
    <p v-if="!!link">
      <a target="_blank" rel="noopener noreferrer" :href="link">{{ text }}</a>
    </p>
  </div>
</template>

<script>
export default {
  name: 'blueCheckbox',

  model: {
    prop: 'checked',
    event: 'change',
  },

  props: {
    text: String,
    link: String,
    disabled: Boolean,
    alreadyChecked: Boolean,
  },

  data() {
    return {
      checked: false,
    }
  },

  watch: {
    alreadyChecked() {
      this.checked = this.alreadyChecked;
    },
  },
}
</script>
