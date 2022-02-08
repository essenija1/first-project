<template>
  <v-simple-table fixed-header height="400px">
    <template v-slot:default>
      <thead>
        <tr>
          <th class="text-left">#</th>
          <th class="text-left">Date</th>
          <th class="text-left">Category</th>
          <th class="text-left">Value</th>
          <th class="text-left">Button</th>
        </tr>
      </thead>
      <tbody>
        <tr
          v-for="(item, idx) in items"
          :key="idx"
          :items-per-page="5"
          class="elevation-1"
        >
          <td>{{ item.idx }}</td>
          <td>{{ item.date }}</td>
          <td>{{ item.category }}</td>
          <td>{{ item.value }}</td>
          <td>
           
             <!-- <slot name="&times;" v-on:click="onClick">&times;</slot> -->
              <!-- <v-select v-model="filter"> -->
              <v-select 
              :items="headers" 
              label="" 
              dense
              >
                <!-- <option value="completed">Добавить</option>
                <option value="deleted">Удалить</option>
                </v-select>  -->
              </v-select>
          
          </td>
       </tr>
      </tbody>
    </template>
  </v-simple-table>
</template>


<!--<template>
  <v-data-table
    :headers="headers"
    :items="all"
    :items-per-page="5"
    class="elevation-1"
  ></v-data-table>
</template>-->





<!--<template>
   <v-container>  
    <v-row>   
      <v-col :cols="1">
        #
      </v-col>
      <v-col>
        Date
      </v-col>
      <v-col>
        Category
      </v-col>
      <v-col :cols="2">
        Value
      </v-col>
      <v-col :cols="3">
        Button
      </v-col>
      </v-row>
      <v-row v-for="(item, idx) in items" :key="idx">
        <v-col :cols="1">{{item.id}}</v-col>
        <v-col>{{item.date}}</v-col>
        <v-col>{{item.category}}</v-col>
        <v-col>{{item.value}}</v-col>      
          <button><slot name="&times;" v-on:click="onClick">&times;</slot>
            <select v-model="filter"> 
              <option value="completed">Добавить</option>
              <option value="deleted">Удалить</option>
           </select></button>
  
    </v-row>
  </v-container>
</template>-->



<script>
export default {
  name: "PaymentsDisplay",
  props: {
    items: {
      type: Array,
      default: () => [],
    },
    headers: {
        type: Array,
        default: () => ['убрать', 'добавить'],
    },
    data() {

      return {
        //filter: 'all',

        items: [
          {
            category: "Education",
          },
          {
            category: "Sport",
          },
          {
            category: "Internet",
          },
          {
            category: "Food",
          },
          {
            category: "Transport",
          },
        ],
    };
    },
   
    watch: {
      filter(value) {
        console.log(value);
      },
    },
  },
};
</script>


<style scoped>
</style>
