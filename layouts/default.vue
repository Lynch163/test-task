<template>
  <header style="padding: 40px; display: flex; align-items: center; justify-content: space-between; margin-bottom: 120px">
    <img src="/images/qtim-logo.svg" alt="logo" @click="useRouter().back()" style="cursor: pointer">

    <div class="nav-group" style="display: flex; align-items: center">
      <div class="menu" style="margin-right: 90px; font-size: 20px">
        <span style="margin-right: 60px; cursor: pointer">Works</span>
        <span style="cursor: pointer">About</span>
      </div>
      <div class="buttons" style="display: flex; align-items: center">
        <img
            src="/images/united-kingdom-ico.svg"
            alt="lang-ico"
            style="margin-right: 16px; cursor: pointer; padding: 10px; border-radius: 999px;"
        />
        <button>Let’s work</button>
      </div>
    </div>
  </header>

  <main style="padding: 0 112px; margin-bottom: 140px;">
    <slot />
  </main>

  <footer style="padding: 140px 120px 0;background-color: #E2BEFF">
    <div style="margin-bottom: 55px">Is there a project?</div>
    <div style="display: flex; justify-content: space-between; margin-bottom: 140px">
      <div style="width: 40%">
        <div style="font-size: 112px; text-decoration: underline; text-decoration-thickness: from-font">
          Let’s work together
        </div>
      </div>
      <div style="width: 40%; display: flex; flex-direction: column; gap: 36px">
        <div>
          <div style="margin-bottom: 12px">For all questions</div>
          <div style="margin-bottom: 4px">+7 (920) 278—00—68</div>
          <div>qtim@agency.com</div>
        </div>
        <div>
          <div style="margin-bottom: 12px">Office in Russia</div>
          <div style="margin-bottom: 8px">139 Ruben Station Lake<br>Drew, NM 52678</div>
          <img src="/images/button-location.svg" alt="">
        </div>
        <div>
          <div style="margin-bottom: 12px">Office in Dubai</div>
          <div style="margin-bottom: 8px">139 Ruben Station Lake<br> Drew, NM 52678</div>
          <img src="/images/button-location.svg" alt="">
        </div>
      </div>
    </div>
    <div style="display: flex; align-items: end; justify-content: space-between">
      <div style="display: flex; gap: 32px; margin-bottom: 30px">
        <a href="#" style="color: #101010">Facebook</a><a href="#" style="color: #101010">Instagram</a><a href="#" style="color: #101010">Telegram</a>
      </div>
      <img src="/images/go-button.svg" alt="" style="cursor: pointer">
      <div style="display: flex; gap: 32px; margin-bottom: 30px">
        <a href="#" style="color: #101010">Behance</a><a href="#" style="color: #101010">Linkedn</a><a href="#" style="color: #101010">Privacy Policy</a>
      </div>
    </div>
  </footer>
</template>
<style>
body {
  margin: 0;
  font-family: "Old Standard TT", serif;
}
</style>

<style lang="scss" scoped>
button {
  padding: 16px 32px;
  background-color: #101010;
  color: #fff;
  font-size: 20px;
  font-weight: 400;
  border-radius: 999px;
  cursor: pointer;
  border: none;
  margin: 0 5px;
}
body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  background-color: #f4f4f4;
}
</style>
<script setup lang="ts">
</script>