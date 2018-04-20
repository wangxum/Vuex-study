<template>
    <div>
    {{count}}
    <child/>
    </div>
</template>
<script>
    import child from './child.vue'
    export default{
        computed:{
            count(){
                return this.$store.state.count;
            }
        },
        components:{
            child
        }
    }    
</script>