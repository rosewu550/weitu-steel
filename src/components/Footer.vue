<template>
  <div class="weitu-footer">
    <div class="footer-column">
      <p>Company Profile</p>
      <div>introduction</div>
      <div>operation philosophy</div>
      <div>service objectives</div>
      <div>organization stucture</div>
      <div>company qualification</div>
    </div>


    <div class="footer-column">
      <p>Construction Management</p>
      <div>safety managment</div>
      <div>quality control</div>
      <div>progress management</div>
    </div>


    <div class="footer-column">
      <p>Overview Of Plant</p>
      <div>plant introduction</div>
      <div>overview</div>
    </div>


    <div class="footer-column">
      <p>Contact Us</p>
      <div>contact information</div>
    </div>

  </div>
</template>

<script>
export default {
  name: "Footer",
  props: {
    title: {
      type: String,
      default: ""
    }
  }
};
</script>

<style lang="scss" scoped>
.weitu-footer {
  width: 60%;
  display: flex;
  justify-content: space-between;
  margin: 30px auto;

  p {
    font-size: 20px;
    font-weight: bold;
  }


  .footer-column {
    display: grid;
    row-gap: 20px;
    grid-template-rows: 30px 30px 30px 30px 30px;
    justify-content: flex-start;
    padding-bottom: 60px;
  }
}


</style>