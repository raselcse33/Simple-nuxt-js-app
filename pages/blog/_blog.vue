<template>
  <div>
    <p>it is underscore log vue {{ slug.blog }}</p>
  </div>
</template>
<script>
export default {
  data() {
    return {
      slug: this.$route.params,
    };
  },
  created() {
    console.log(this.$route.params);
  },
};
</script>
