<template>
  <div class="row">
    <div clas="col-sm-12">
      <h1 v-if="showTitle">{{ msg }}</h1>
      <button class="btn btn-primary" v-on:click="showTitle = !showTitle">Alternar</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Olá, GDG!',
      showTitle: true
    }
  }
}
</script>
