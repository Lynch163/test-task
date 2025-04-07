<template>
  <header>
    <img src="/images/qtim-logo.svg" alt="logo" @click="useRouter().back()">
    <div class="nav-group">
      <div class="menu">
        <span>Works</span>
        <span>About</span>
      </div>
      <div class="buttons">
        <img
            src="/images/united-kingdom-ico.svg"
            alt="lang-ico"
        />
        <button>Let’s work</button>
      </div>
    </div>
  </header>

  <main>
    <slot />
  </main>

  <footer>
    <div>Is there a project?</div>
    <div>
      <div>
        <div>
          Let’s work together
        </div>
      </div>
      <div>
        <div>
          <div>For all questions</div>
          <div>+7 (920) 278—00—68</div>
          <div>qtim@agency.com</div>
        </div>
        <div>
          <div>Office in Russia</div>
          <div>139 Ruben Station Lake<br>Drew, NM 52678</div>
          <img src="/images/button-location.svg" alt="">
        </div>
        <div>
          <div>Office in Dubai</div>
          <div>139 Ruben Station Lake<br> Drew, NM 52678</div>
          <img src="/images/button-location.svg" alt="">
        </div>
      </div>
    </div>
    <div>
      <div>
        <a href="#">Facebook</a>
        <a href="#">Instagram</a>
        <a href="#">Telegram</a>
      </div>
      <img src="/images/go-button.svg" alt="">
      <div>
        <a href="#">Behance</a>
        <a href="#">Linkedn</a>
        <a href="#">Privacy Policy</a>
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
header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 40px;
  margin-bottom: 120px;
  & img {
    cursor: pointer;
  }
}

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

.nav-group {
  display: flex;
  align-items: center;
}

.menu {
  display: flex;
  gap: 60px;
  margin-right: 90px;
  font-size: 20px;
  cursor: pointer;
}

.buttons {
  display: flex;
  align-items: center;
  & img {
    margin-right: 16px;
    cursor: pointer;
    padding: 10px;
    border-radius: 999px;
  }
}

main {
  padding: 0 112px;
  margin-bottom: 140px;
}

footer {
  padding: 140px 120px 0;
  background-color: #E2BEFF;

  & > *:nth-child(1) {
    margin-bottom: 55px;
  }

  & > *:nth-child(2) {
    display: flex;
    justify-content: space-between;
    margin-bottom: 140px;
    & > *:nth-child(1) {
      width: 40%;
      & div {
        font-size: 112px;
        text-decoration: underline;
        text-decoration-thickness: from-font;
      }
    }
    & > *:nth-child(2) {
      width: 40%;
      display: flex;
      flex-direction: column;
      gap: 36px;
      & > *:nth-child(1) {
        & > *:nth-child(1) {
          margin-bottom: 12px;
        }
        & > *:nth-child(2) {
          margin-bottom: 4px;
        }
      }
      & > *:not(:first-child) {
        & > *:nth-child(1) {
          margin-bottom: 12px;
        }
        & > *:nth-child(2) {
          margin-bottom: 8px;
        }
      }
    }
  }

  & > *:nth-child(3) {
    display: flex;
    align-items: end;
    justify-content: space-between;
    & > *:nth-child(1),
    & > *:nth-child(3) {
      display: flex;
      gap: 32px;
      margin-bottom: 30px;
      & a {
        color: #101010;
      }
    }
    & img {
      cursor: pointer;
    }
  }
}
</style>