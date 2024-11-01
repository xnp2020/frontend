<script>
export default {
  data() {
    return {
      msg:"Hello Vue 3.0 + Vite",
      hello:"hello",
      ok:true,
      message:"大家好",
      rawHtml:"<em>hello</em>"
    }
  }
}
</script>

<template>
<h3>模板语法</h3>
<p>{{ msg }}</p>
<p>{{ hello + 'world' }}</p>
<p>{{ ok ? 'Yes' : 'No' }}</p>
<p>{{ message.split("").reverse().join("") }}</p>
<!-- <p>{{ if (ok) {return message} }}</p> -->
<p v-html="rawHtml"></p>
</template>


