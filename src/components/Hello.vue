<template>
  <div class="hello">
    <div class="container">
      <div class="col-md-12">
        <ul class="list-group">
          <li class="list-group-item" v-for="data in datas">
            <a href="#" target="_blank">{{data}}</a>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  props: ['datas']

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import '../../node_modules/bootstrap/dist/css/bootstrap.min.css';

h1, h2 {
  font-weight: normal;
}


.list-group-item {
  text-align: left;
}


/*a {
  color: #42b983;
}*/
</style>
