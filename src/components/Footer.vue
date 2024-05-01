<template>
  <div class="footer-root">
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

.footer-root {
  background: #000000;
}

.weitu-footer {
  width: 60%;
  display: flex;
  justify-content: space-between;
  margin: 0 auto;
  padding: 40px 0;

  p {
    color: white;
    font-size: 20px;
    font-weight: bold;
  }


  .footer-column {
    color: #969baa;
    display: grid;
    row-gap: 20px;
    grid-template-rows: 30px 30px 30px 30px 30px;
    justify-content: flex-start;
    padding-bottom: 60px;
  }
}


</style>