<template>
  <div id="app" class="container">
    <button @click="selectedComponent = 'appQuote'">Quote</button>
    <button @click="selectedComponent = 'appAuthor'">Author</button>
    <button @click="selectedComponent = 'appNew'">New</button>
    <hr>
    <p>{{ selectedComponent }}</p>
    <keep-alive>
      <component :is="selectedComponent">
        <p>Default Content</p>
      </component>
    </keep-alive>
<!--    <app-quote>
      <h2 slot="title">{{ quoteTitle }}</h2>
      <p>A wonderful quote!</p>
    </app-quote>-->
  </div>
</template>

<script>
  import Quote from './components/Qoute'
  import New from './components/New'
  import Author from './components/Author'
export default {
      data : function(){
        return{
            quoteTitle : 'The Quote',
            selectedComponent : 'appQuote'
        }
      },
    components: {
        appQuote : Quote,
        appNew : New,
        appAuthor : Author
    }
}
</script>

<style scoped>

</style>
