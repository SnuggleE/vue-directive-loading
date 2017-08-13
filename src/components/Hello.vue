<template>
  <div class="hello">
    <div class="loading-container" loading-options="{time:12345}" v-loading="isLoading">
      <div>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Dicta dolor fuga in magni minus quas quasi ratione
        sapiente tenetur vel. Asperiores enim esse et expedita nulla porro qui sequi veritatis!
      </div>
      <div>Ab adipisci, aliquam blanditiis, consequatur delectus dolor esse est eum facere illum ipsum laborum magni
        modi nobis officiis quia quisquam repellat reprehenderit sit suscipit temporibus ullam unde veniam veritatis
        vero?
      </div>
      <div>Accusamus accusantium amet eius error fuga officia quos repellat tempore ut vel. A aliquam, aliquid autem
        corporis facilis ipsum laudantium libero maiores mollitia, nesciunt nostrum, quia quo sequi temporibus vero.
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: 'hello',
  directives:{
      loading:{
          bind:function (el) {
//              console.log(el)
              console.log(eval('('+el.getAttribute('loading-options')+')').time)
//              console.log('('+el.getAttribute('loading-options')+')')
          },
          inserted:function (el,binding) {
//            console.log(binding);
//            el.style.background="rgba(222,222,222,0.1)";
//            let circle=document.createElementNS()
            let sondiv=document.createElement('div');
//            sondiv.style.background="rgba(244,244,244,0.6)";
            el.style.position='relative';

            sondiv.className="son";

            el.appendChild(sondiv)
          },
      }
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      isLoading:{
          visible:false,
        text:'加载中。。。'
      },
      options:{time:12321}
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
div.loading-container{
  width: 100%;
  height: 300px;
  /*background: #2c3e50;*/
  border: 1px solid red;
}
div.son{
  height: 100%;
  width: 100%;
  position:absolute;
  top:0;
  left:0;
  background: rgba(255, 255, 255, 0.9);
  z-index: 1000;
}
</style>
