<template>
    <v-app>
        <ToolBar />  
    <v-content>
      <v-container>
        <nuxt />
      </v-container>
    </v-content>    
    <v-footer :fixed="fixed" app >
      <span>&copy; 2019  ::  portafolio miguelo</span>
    </v-footer>
    </v-app>  
</template>
<script>
export default {
    components: {
        ToolBar: () => import('@/components/Toolbar')
    },
    data : () =>({
        fixed: false,
    })
}
</script>

