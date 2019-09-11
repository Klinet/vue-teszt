<template>
  <div id="tasks">
    <hr>
    <h1>ListItem.vue</h1>
  </div>
</template>

<script>
export default {
  name: 'ListItem',
  props: ["index", "item", "active"],
  data: function () {
    return {

    }
  },
  //template : '<div v-for="(task, index) in tasks"' +
  template : '<div v-bind:class="{ active : active, task : true }">' +
                '<div class="title" v-on:click="select(index)">{{task.name}}</div>' +
                '<div class="context">' +
                    '<i v-on:click="deleteTask(index, task.id)" class="fas fa-trash-alt"><i>' +
                '</div>'+
            '</div>',
  methods : {
    select : function (index) {
      this.$emit('select', index);
      /*if (this.isActive(index)) {
        this.selected = -1;
      } else {
        this.selected = index;
      }*/
    },
    deleteTask : function (index, id) {
       this.$emit('delete', index, id)
        /*this.$http.delete("/task/" + id).then(function() {
          this.tasks.splice(index,1);
          this.selected = -1;
          this.$emit('message', "Deleted!")
      }).catch(this.httpError);*/
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
