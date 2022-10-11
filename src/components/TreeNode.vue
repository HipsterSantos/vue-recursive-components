<template>
    <div class="node-item">
        {{node.label}}
        <div v-if="hasChildren" class="children-node">
            <TreeNodeComponent v-for="(child) in node.children" :key="child.id" :node="child"/>
        </div>
    </div>
</template>

<script>
export default {
    name:'TreeNodeComponent',
    props:{
        node:{
            type: Object,
            required:true 
        }
    },
    data(){
        return {}
    },
    computed:{
        hasChildren(){
            let {children} = this.node
            return  children && children.length > 0
        }
    },
    mounted(){
        console.log('treenode component is mounted ')
    }
}
</script>

<style scoped>
.node-item{
    padding: 1em;
    width:200px;
    background: rgb(80, 80, 186);
    font-size: 17pt;
    font-style: normal;
    border-radius: 1em;
    color:#fff;
    font-weight: 700;
    margin: 1em 0;
    
}
.children-node{
    background: rgb(51, 119, 40);
    margin: 1em 0.3em
}
</style>