<script lang="ts">
  import WindowsIcon from '@/components/icons/WindowsIcon.vue';
  import { defineComponent, reactive } from 'vue';
  import AccountView from '@/views/AccountView.vue';
  import router from '@/router';

  export default defineComponent({
    components: {
      WindowsIcon,
      AccountView,
    },
    setup() {
      const formState = reactive({
        email: '',
        password: '',
      });
      const onFinish = (values: any) => {
        if (values.email !== 'admin' || values.password !== 'admin') {
          alert('Wrong credentials');
          return;
        } else {
          alert('Success');
          localStorage.setItem('token', 'allow-to-enter' )
          router.push({ name: 'account' })
        }
      };
      const onFinishFailed = (errorInfo: any) => {
        console.log('Failed:', errorInfo);
      };
      return {
        formState,
        onFinish,
        onFinishFailed,
      };
    },
  });

</script>

<template>
    <a-form
        :model="formState"
        :label-col="{ span: 24 }"
        :wrapper-col="{ span: 24 }"
        name="basic"
        class="login-form"
        autocomplete="off"
        @finish="onFinish(formState)"
        @finishFailed="onFinishFailed"
    >
      <h2 class="form-title">Log in</h2>
      <a-form-item
          class="form-label"
          label="Email"
          :label-col="{ span: 24 }"
          name="email"
          :rules="[{ required: true, message: 'Please input your username!' }]"
      >
        <a-input
            class="form-input"
            v-model:value="formState.email" />
      </a-form-item>

      <a-form-item
          class="form-label"
          label="Password"
          name="password"
          :rules="[{ required: true, message: 'Please input your password!' }]"
      >
        <a-input-password
            v-model:value="formState.password"
            class="form-input"
        />
      </a-form-item>

      <a-button type="primary" class="form-button" html-type="submit">Login</a-button>
      <div class="or-block">
        <div class="or-block__line"></div>
        <div class="or-block__text">or</div>
        <div class="or-block__line"></div>
      </div>
      <a-button type="primary" class="microsoft-button" html-type="submit">
        <WindowsIcon />
        Log in with Microsoft
      </a-button>
    </a-form>
</template>

<style scoped>
  .login-form {
    position: relative;
    left: 10%;
    margin-top: 66px;
    background: #FFFFFF;
    border-radius: 8px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: flex-start;
    padding: 69px 94px 49px;
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
    /*height: 80px;*/
    display: flex;
    flex-direction: row;
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
    width: 100%;
    border: 1px solid #DADADA;
    border-radius: 4px;
    height: 40px;
    padding: 12px 16px;
  }

  .form-button {
    width: 100%;
    background: #1EC0D6;
    height: 40px;
    border: none;
    border-radius: 4px;
    font-size: 16px;
    font-weight: 600;
    line-height: 22px;
    letter-spacing: 0;
    color: #FFFFFF;
    padding: 0;
    justify-content: center;
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
    height: 40px;
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
    text-shadow: none;
  }
</style>
