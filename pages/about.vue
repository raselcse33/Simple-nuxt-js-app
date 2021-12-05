<template>
  <div>
    <p>{{title}} Page</p>
  </div>
</template>
<script>
export default {
  asyncData() {
    return{
      title:'About'
    }
  },
  head() {
    return{
      title:'about-page',
      script:[
        {
          src:'/about.js'
        }
      ],
      meta:[
        {
          hid:'description',
          name:'description',
          content:'this is about page'
        }
      ]
    }

  },
}
</script>
