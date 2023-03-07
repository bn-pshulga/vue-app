<script setup lang="ts">
  import WindowsIcon from '@/components/icons/WindowsIcon.vue';
</script>

<template>
  <form>
    <h2 class="form-title">Log in</h2>
    <label class="form-label" for="email">
      Email
      <input class="form-input" type="email"/>
    </label>
    <label class="form-label" for="password">
      Password
      <input class="form-input" type="password"/>
    </label>
    <button type="submit" class="form-button">Login</button>
    <div class="or-block">
      <span class="or-block__line"></span>
      <span class="or-block__text">or</span>
      <span class="or-block__line"></span>
    </div>
    <button type="submit" class="microsoft-button">
      <WindowsIcon />
      Log in with Microsoft
    </button>
  </form>
</template>

<style scoped>
  form {
    margin-top: 66px;
    background: #FFFFFF;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    padding: 69px 94px 49px;
    height: 554px;
    width: 473px;
  }

  .form-title {
    margin-bottom: 30px;
    font-size: 32px;
    font-weight: 400;
    line-height: 44px;
    letter-spacing: 0;
  }

  .form-label {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: flex-start;
    gap: 8px;
    margin-bottom: 30px;
    width: 100%;
    font-size: 13px;
    font-weight: 400;
    line-height: 18px;
    letter-spacing: 0;
    color: #383E54;
  }

  .form-input {
    border: 1px solid #DADADA;
    border-radius: 4px;
    height: 40px;
    width: 100%;
    padding: 12px 16px;
  }

  .form-button {
    background: #1EC0D6;
    height: 40px;
    width: 100%;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    font-weight: 600;
    line-height: 22px;
    letter-spacing: 0;
    color: #FFFFFF;
  }

  .or-block {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    gap: 16px;
    margin-top: 38px;
    width: 100%;
    margin-bottom: 30px;
  }

  .or-block__line {
    width: 100%;
    height: 1px;
    background: #DADADA;
  }

  .or-block__text {
    font-size: 16px;
    font-weight: 300;
    line-height: 22px;
    letter-spacing: 0;
    color: #B6B6B6;
  }

  .microsoft-button {
    border: 1px solid #1EC0D6;
    border-radius: 4px;
    padding: 9px 0;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 11px;
    background: transparent;
    color: #545454;
    font-size: 16px;
    font-weight: 600;
    line-height: 22px;
    letter-spacing: 0;
  }

</style>
