<template>
<div>
    <welcome />
    <recent />    
    <services />
    <aboutMe />
    <contact />
</div>
</template>

<script>
export default {
  layout: 'wrapper',
  components: {    
    Welcome: () => import('@/pages/welcome'),
    Recent: () => import('@/pages/recent'),
    Services: () => import('@/pages/services'),
    AboutMe: () => import('@/pages/aboutMe'),
    Contact: () => import('@/pages/contact')
  }
}
</script>
