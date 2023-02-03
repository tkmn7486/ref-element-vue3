<template>
  <div id="app">
    <div class="function-preview">
      <h3>【各変数の中身】</h3>
      <table class="table">
        <tr>
          <th>変数</th>
          <th>中身</th>
        </tr>
        <tr>
          <td>メイン-inputの入力文字</td>
          <td>{{input_word_main}}</td>
        </tr>
        <tr>
          <td>メイン-inputのref</td>
          <td>{{ref_main}}</td>
        </tr>
        <tr>
          <td>サブ-inputの入力文字</td>
          <td>{{input_word_sub}}</td>
        </tr>
        <tr>
          <td>サブ-inputのref</td>
          <td>{{ref_sub}}</td>
        </tr>
      </table>
    </div>

    <!-- メインのinput要素 -->
    <label>メイン：</label><input type="text" v-model="input_word_main" ref="ref_main">
    <br>

    <!-- サブのinput要素 -->
    <label>サブ：</label><input type="text" v-model="input_word_sub" ref="ref_sub">
    <br>
    <br>

    <!-- メインinputにフォーカスさせるボタン -->
    <button class="btn" @click="focusMain()">メインinputにfocus</button>

    <!-- サブinputにフォーカスさせるボタン -->
    <button class="btn" @click="focusSub()">サブinputにfocus</button>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  name: 'App',
  setup(){
    let ref_main = ref()
    let ref_sub = ref()

    let input_word_main = ref("")
    let input_word_sub = ref("")

    const focusMain=()=>{
      ref_main.value.focus();
    }

    const focusSub=()=>{
      ref_sub.value.focus();
    }

    return{
      ref_main,
      ref_sub,
      input_word_main,
      input_word_sub,
      focusMain,
      focusSub
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.table{
  margin: 0 auto;
  padding: 10px;
}

.function-preview{
  border: 1px solid;
  margin: 20px;
}

.btn{
  margin: 20px;
}
</style>
