<template>
  <div class="about">
    <div class="about-header">
      Всем привет!<br />
      На данном сайте можно максимально подробно ознакомиться с моим
      творчеством,<br />
      найти множество интересных подробностей, связанных с костюмами, образами и
      прочим.
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
};
</script>

<style scoped>
.about {
  position: relative;
  margin: auto;
  margin-top: 50px;
  width: 90%;
  height: 100vh;
  border: 1px solid #fff;
  .about-header {
    margin: auto;
    text-align: left;
    font-size: 28px;
    color: #fff;
  }
}
</style>
