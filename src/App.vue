<template>
  <div id="app">
    <h1>{{ msg }}</h1>
    <button @click="update" class="btn btn-success">add new</button>
    <hello :datas="datas"></hello>
    <div class="mask" :class="{addnew: isAddNew}">
      <div class="container">
        <form class="form-horizontal" role="form" @submit.prevent="submit">
          <div class="form-group">
            <label for="inputEmail3" class="col-sm-2 control-label">Email</label>
            <div class="col-md-10">
              <input v-model="newItem" type="text" class="form-control"  id="inputEmail3" placeholder="Username">
            </div>
          </div>
          <div class="form-group">
            <div class="col-md-offset-2">
              <button type="submit" class="btn btn-default">Sign in</button>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
import Hello from './components/Hello'

export default {
  name: 'app',
  data () {
    return {
      msg: 'To do list',
      isAddNew: false,
      datas: [],
      newItem: ''
    }
  },
  methods: {
    addNew () {
      this.isAddNew = true
    },
    submit () {
      this.isAddNew = false
      this.datas.push(this.newItem)
      this.newItem = ''
    },
    update () {
      console.log('update new item')
      var self = this
      setTimeout(function () {
        self.datas.push('add new automatic')
        // self.$nextTick(function () {
        //   console.log(JSON.stringify(self.datas))
        // })
      }, 3000)
    }
  },
  components: {
    Hello
  }
}
</script>

<style>

@import '../node_modules/bootstrap/dist/css/bootstrap.min.css';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.mask {
  position: absolute;
  background-color: rgba(0, 0, 0, 0.5);
  top: 0;
  width: 100%;
  height: 100%;
  visibility: hidden;
}

.addnew {
  visibility: visible;;
}

.center {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background-color: green;
}

form {
  margin-top: 400px;
}

.form-horizontal .form-group {
     margin-left: 0;
    /* margin-left: -15px;*/
}
</style>
