<template>
  <child
    v-model="value"
    :alreadyChecked="value"
    @change="changeValue"
    :text="'I am the child'"
  />
</template>

<script>
import Child from './components/Child.vue';

export default {
  name: 'Parent',

  components: {
    Child,
  },

  data() {
    return {
      value: false,
    }
  },

  mounted() {
    this.changeValueOnMount();
  },

  methods: {
    changeValueOnMount() {
      setTimeout(() => {
        this.value = true;
      });
    },

    changeValue() {
      this.value = !this.value;
    },
  },
}
</script>
