<template>
  <div class="links">
    <icon-link src="facebook.svg" alt="facebook icon" href="https://www.facebook.com/Hi7Haut" class="link"/>
    <icon-link src="instagram.svg" alt="instagram icon" href="https://www.instagram.com/hi7_haut/?hl=fr" class="link"/>
    <icon-link src="tiktok.svg" alt="tiktok icon" href="https://www.tiktok.com/@hi7_haut?lang=fr" class="link"/>
  </div>
</template>

<script>
export default {
  name: "links-item"
}
</script>

<style lang="scss" scoped>
.links {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 120px;
  margin: 10px;
}

.link {

  height: 30px;
  width: 30px;

}
</style>
