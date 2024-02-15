<script>

export default {
  name: 'App',
  data() {
    return {
      inputStr: '',
      result: ''
    }
  },

  methods: {
    updateDisplay(val) {
      this.inputStr = this.inputStr + val
    },
    calculate() {
      this.result = eval(this.inputStr)
      this.inputStr = this.result
    },
    clearDisplay() {
      this.inputStr = ''
    }
  },
}
</script>

<template>
  <body>
    <div class="container p-5">
      <div class="col-auto ">
        <!-- <div class="display"> -->
        <form action="" class="form-group p-0 d-flex justify-content-between" @submit.prevent="calculate">
          <input type="text" v-model="inputStr">
          <input type="submit" value="=">
        </form>
        <!-- </div> -->
      </div>

      <div class="buttons">
        <div class="row d-flex justify-content-between">
          <div class="col-auto ">
            <button @click="() => updateDisplay('+')" class="btn btn-info">+</button>
            <button @click="() => updateDisplay('-')" class="btn btn-info">-</button>
            <button @click="() => updateDisplay('*')" class="btn btn-info">*</button>
            <button @click="() => updateDisplay('/')" class="btn btn-info">/</button>
          </div>
        </div>

        <div class="row d-flex justify-content-between">
          <div class="col-auto ">
            <button @click="() => updateDisplay('1')" class="btn btn-warning">1</button>
            <button @click="() => updateDisplay('2')" class="btn btn-warning">2</button>
            <button @click="() => updateDisplay('3')" class="btn btn-warning">3</button>
            <button @click="() => clearDisplay('/')" class="btn btn-success">C</button>
          </div>
        </div>

        <div class="row d-flex justify-content-between">
          <div class="col-auto ">
            <button @click="() => updateDisplay('4')" class="btn btn-warning">4</button>
            <button @click="() => updateDisplay('5')" class="btn btn-warning">5</button>
            <button @click="() => updateDisplay('6')" class="btn btn-warning">6</button>
            <button @click="() => updateDisplay('.')" class="btn btn-warning">.</button>
          </div>
        </div>

        <div class="row d-flex justify-content-between">
          <div class="col-auto ">
            <button @click="() => updateDisplay('7')" class="btn btn-warning">7</button>
            <button @click="() => updateDisplay('8')" class="btn btn-warning">8</button>
            <button @click="() => updateDisplay('9')" class="btn btn-warning">9</button>
            <button @click="() => updateDisplay('0')" class="btn btn-warning">0</button>
          </div>
        </div>
      </div>
    </div>
  </body>
</template>

<style>
.btn {
  margin: 8px;
  width: 50px;
  height: 50px;
}
</style>
