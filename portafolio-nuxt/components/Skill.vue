<template>       
    <v-layout wrap flat>
          <v-flex md6 xs12
            v-for="(item, i) in items"
            :key="i"
            pa-4
        >        
        <v-flex
          xs12              
          v-text="item.name"
          tercero--text
        />
        <v-flex
          xs12
          text-xs-right
          v-text="`${item.value}%`"
        />
        <v-progress-linear
          :value="item.value"
          color="tercero"
          height="8"
        />

        </v-flex>        
    </v-layout>  
</template>
<script>
export default {
  name: "skill",  
  data: () => ({
    items: [      
      { name: 'Web Development', value: 90},
      { name: 'Desktop app', value: 90 },      
      { name: 'C#', value: 70 },      
      { name: 'Java', value: 90 },      
      { name: 'Cloud computing', value: 70 }
    ]
  })
}
</script>
