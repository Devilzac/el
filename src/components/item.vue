<template>
   <div>
     <table>
       <tbody>
         <tr>
           <td>hola</td>
         </tr>
       </tbody>
     </table>
   </div>
</template>

<script>
import Axios from 'axios';

export default {
  data() {
    return {
      titulo: null,
    };
  },
  mounted() {
    this.getInfo();
  },
  methods: {
    getInfo() {
      Axios.get('https://cat-fact.herokuapp.com').then((response) => {
        console.log('response: ', response);
      }).catch((e) => {
        console.log(e);
      });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
</style>
