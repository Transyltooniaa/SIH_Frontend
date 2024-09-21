<template>
  <div id="app">
    <aside class="sidebar">
      <div class="logo">NaturalReader</div>
      <button class="add-files-btn">+ Add Files</button>
      <nav class="menu">
        <a href="#" class="menu-item">Library</a>
        <a href="#" class="menu-item">Account</a>
        <a href="#" class="menu-item">Apps</a>
        <a href="#" class="menu-item">AI Voice Generator</a>
      </nav>
      <div class="bottom-section">
        <div class="auth-buttons">
          <button class="login-btn">Login / Sign Up</button>
          <button class="upgrade-btn">Upgrade</button>
        </div>
      </div>
    </aside>

    <main class="main-content">
      <header class="top-bar">
        <div class="controls">
          <button class="btn">⟳</button>
          <button class="btn">⏯</button>
          <span>1x</span>
        </div>
      </header>

      <section class="content-area">
        <div class="content-box"></div>
      </section>
    </main>
  </div>
</template>

<script>
export default {
  name: 'App',
};
</script>

<style scoped>
#app {
  display: flex;
  height: 100vh;
  background-color : #f1f1f1;
}

.sidebar {
  width: 250px;
  background-color: #fff;
  padding: 20px;
  border-right: 1px solid #e5e5e5;
}

.logo {
  font-size: 20px;
  font-weight: bold;
  margin-bottom: 20px;
}

.add-files-btn {
  display: block;
  width: 100%;
  background-color: #007bff;
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
  font-size: 16px;
  text-align: center;
  margin-bottom: 20px;
}

.menu-item {
  display: block;
  color: #000;
  padding: 10px 0;
  text-decoration: none;
}

.bottom-section {
  position: absolute;
  bottom: 20px;
  width: 90%;
}

.qr-section img {
  width: 100%;
}

.auth-buttons {
  margin-top: 20px;
}

.login-btn, .upgrade-btn {
  display: block;
  width: 100%;
  padding: 10px;
  border: none;
  cursor: pointer;
  font-size: 16px;
  margin-bottom: 10px;
}

.upgrade-btn {
  background-color: #007bff;
  color: white;
}

.main-content {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}

.top-bar {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 20px;
  background-color: #fff;
  border-bottom: 1px solid #e5e5e5;
}

.profile-pic {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}

.controls {
  display: flex;
  align-items: center;
}

.btn {
  background: none;
  border: none;
  font-size: 18px;
  margin: 0 10px;
  cursor: pointer;
}

.content-area {
  flex-grow: 1;
  padding: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.content-box {
  width: 80%;
  height: 80%;
  background-color: #f1f1f1;
  border-radius: 10px;
  box-shadow: 0px 4px 12px rgba(0, 0, 0, 0.1);
}
</style>
