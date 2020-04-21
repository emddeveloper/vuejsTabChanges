<template>
  <div class="stage2">
    <h1>Stage 2</h1>
   
 <!-- Button trigger modal -->
<button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
  Stage-2 Modal
</button>

<!-- Modal -->
<div class="modal fade" id="exampleModal"  role="dialog" aria-labelledby="exampleModalLabel" aria-hidden="true">
  <div class="modal-dialog" role="document">
    <div class="modal-content">
      <div class="modal-header">
        <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
          <span aria-hidden="true">&times;</span>
        </button>
      </div>
      <div class="modal-body">
       <modal modalstage="modal opening from stage-2"></modal>
      </div>
      <div class="modal-footer">
        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
        <button type="button" class="btn btn-primary">Save changes</button>
      </div>
    </div>
  </div>
</div>

   <button @click="back">Back</button>
  </div>
</template>

<script>
import modal from "./modal.vue";
export default {
  name: 'stage2',
  components:{
modal
  },
  data(){
      return{
          backstage:1
      }
  },
  methods:{
       back: function(){
           this.$emit('backstage',this.backstage)
       }
  }
  
}
</script>