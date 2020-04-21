<template>
  <div class="modalcontent">
    <h1>ThisModal opening from {{modalstage}}</h1>
    <div>
        <input v-model.number="member">
        <button @click="addmember" data-dismiss="modal">Add Member</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'modal',
    props:['modalstage'],
    data(){
        return{
            member:0
        }
    },
    methods:{
        addmember: function(){
            this.$emit('getmember',this.member)
        }
    }
  
}
</script>