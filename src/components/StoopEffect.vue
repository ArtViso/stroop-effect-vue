<template>
  <header>
    <img alt="Vue logo" style="width:50px; height:50px" src="../assets/logo.png">
    <h1>{{ msg }}</h1>
  </header>
  <section>
    <h1>WORDS:</h1>
    <div class="box">
      <span>RED</span>
   </div>
  </section>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  props: {
    msg: String
  }
})
export default class StroopEffect extends Vue {
  msg!: string
}
</script>

