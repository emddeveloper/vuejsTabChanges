<template>
  <div class="stage1">
    <h1>stage {{stage}}</h1>
 
 <div class="member">
     <p >{{members}}</p>
 </div>
    <!-- Button trigger modal -->
    <button type="button" class="btn btn-primary" data-toggle="modal" data-target="#exampleModal">
    Stage-1 Modal
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
        <modal modalstage="modal opening from stage-1" @getmember="addmember"></modal>
        </div>
        <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
            <button type="button" class="btn btn-primary">Save changes</button>
        </div>
        </div>
    </div>
    </div>

    <button @click="proceed">Proceed</button>
  </div>
</template>

<script>
import modal from "./modal.vue";
export default {
  name: "stage1",
  components: {
    modal
  },
  data() {
    return {
      stage: 1,
      nextStage: 2,
      members:null
    };
  },
  methods: {
    proceed: function() {
      this.$emit("proceed-stage", this.nextStage);
    },
    addmember: function(x){
        this.members=x
    }
  }
};
</script>