<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <TreeNode v-for="(node,index) in nodes" :key="index" :node="node"/>
    Welcome to vue-tree-view by using recursive call 
  </div>
</template>

<script>
import TreeNode from './TreeNode.vue'
export default {
  name: 'HomeComponent',
  components:{
    'TreeNode':TreeNode
  },
  props: {
    msg: String
  },
  computed: {
    nodes() {
      return [
        {
          id: 1,
          label: 'Foods',
          children: [
            {
              id: 2,
              label: 'Fruits',
              children: [
                {
                  id: 3,
                  label: 'Banana'
                },
                {
                  id: 4,
                  label: 'Apple'
                },
                {
                  id: 5,
                  label: 'Strawberry'
                }
              ]
            },
            {
              id: 6,
              label: 'Vegetables',
              children: [
                {
                  id: 7,
                  label: 'Carrot'
                },
                {
                  id: 8,
                  label: 'Lettuce'
                },
                {
                  id: 9,
                  label: 'Potato'
                }
              ]
            }
          ]
        },
        {
          id: 10,
          label: 'Drinks',
          children: [
            {
              id: 11,
              label: 'Beers',
              children: [
                {
                  id: 12,
                  label: 'Budweiser'
                },
                {
                  id: 13,
                  label: 'Heineken'
                }
              ]
            },
            {
              id: 14,
              label: 'Wines'
            },
            {
              id: 15,
              label: 'Whiskey'
            }
          ]
        }
      ]
    }
}//computed property ending 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
