<template>
  <div class="register-page">
    <div class="form">
      <img
        class="login-logo"
        src="@/assets/images/JoomakLogo_login.svg"
        alt="JoomakLogo"
      />
      <h1>
        회원가입
      </h1>
      <form
        class="register-form"
        @submit="checkForm"
        action="/check"
        method="post"
      >
        <div class="form-group">
          <label for="username">아이디 </label>
          <div class="row">
            <input
              type="text"
              id="username"
              class="input-control"
              v-model="username"
            />
            <button class="input-button">중복 체크</button>
          </div>
          <p class="error-message" v-if="errors.username">
            {{ errors.username }}
          </p>
          <!-- <div class="valid-feedback" v-if="validation.valid.firstName">{{ validation.valid.firstName }}</div> -->
        </div>

        <div class="form-group">
          <label for="password">비밀번호 </label>
          <!-- <input type="password" id="password" class="input-control" /> -->
          <input
            type="text"
            id="password"
            class="input-control"
            v-model="password"
          />
          <p class="error-message" v-if="errors.password">
            {{ errors.password }}
          </p>
        </div>
        <div class="form-group">
          <label for="password-confirm">비밀번호 확인</label>
          <!-- <input type="password" id="password-confirm" class="input-control" /> -->
          <input
            type="text"
            id="password-confirm"
            class="input-control"
            v-model="password_confirm"
          />
          <p class="error-message" v-if="errors.password_confirm">
            {{ errors.password_confirm }}
          </p>
        </div>
        <div class="form-group">
          <label for="name">이름 </label>
          <input type="text" id="name" class="input-control" v-model="name" />
        </div>

        <div class="form-group">
          <label for="email">이메일</label>
          <div class="row">
            <input
              type="text"
              id="email-front"
              class="input-control"
              v-model="email_front"
            /><span>@ &nbsp;</span>
            <!-- <input type="text" id="email-back" class="input-control" /> -->
            <select id="email-back" class="input-control" v-model="email_back">
              <option value="naver.com">naver.com</option>
              <option value="gmail.com">gmail.com</option>
            </select>

            <button class="input-button">인증 요청</button>
          </div>
        </div>

        <div class="form-group">
          <label for="email-confirm"> </label>
          <div class="row">
            <input
              type="text"
              id="email-confirm"
              class="input-control"
              placeholder="인증번호 입력"
              v-model="email_confrim"
            />
            <button class="input-button">확인</button>
          </div>
        </div>
        <div class="form-group">
          <label for="phone">휴대폰 번호</label>
          <div class="row">
            <!-- <input type="text" id="phone-front" class="input-control" /> -->
            <select
              id="phone-front"
              class="input-control"
              v-model="phone_front"
            >
              <option value="010">010</option>
            </select>
            <span>- &nbsp;</span>
            <input
              type="text"
              id="phone-middle"
              class="input-control"
              v-model="phone_middle"
            /><span>- &nbsp;</span>
            <input
              type="text"
              id="phone-back"
              class="input-control"
              v-model="phone_back"
            />
          </div>
        </div>
        <div class="form-group">
          <div class="row">
            <button id="additional">추가 정보</button>
          </div>
        </div>
        <div class="form-group">
          <label for="birth">생년월일</label>
          <div class="row">
            <!-- <input type="text" id="year" class="input-control" /> -->
            <select id="year" class="input-control"></select>
            <span>년 &nbsp;</span>
            <input
              type="text"
              id="month"
              class="input-control"
              v-model="birth"
            /><span>월 &nbsp;</span>
            <input type="text" id="day" class="input-control" /><span>일</span>
          </div>
        </div>

        <div class="form-group">
          <label for="nickname">별명</label>
          <input
            type="text"
            id="nickname"
            class="input-control"
            v-model="nickname"
          />
        </div>
        <div class="form-group">
          <label for="gender">성별</label>
          <div class="row">
            <select id="gender" class="input-control" v-model="gender">
              <option value="남">남</option>
              <option value="여">여</option>
            </select>
          </div>
        </div>

        <div class="form-group">
          <button type="submit" class="input-button">확인</button>
          <!-- <input type="submit" value="Submit" /> -->
        </div>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      errors: {
        username: "",
        password: "",
        password_confirm: "",
        name: "",
        phone: "",
      },
      username: "",
      password: "",
      password_confirm: "",
      name: "",
      email: "",
      email_confirm: "",
      phone: "",
      birth: "",
      nickname: "",
      gender: "",
    };
  },
  methods: {
    checkForm(e) {
      e.preventDefault();
      this.errors = { username: "", password: "", name: "", phone: "" };
      if (!this.usename) {
        this.errors = { ...this.errors, username: "아이디 필수" };
      }
      if (!this.name) {
        this.errors = { ...this.errors, name: "이름은 필수" };
      }
      if (!this.email) {
        this.errors = { ...this.errors, email: "이메일 필수" };
      }
      if (!this.password) {
        this.errors = { ...this.errors, password: "비밀번호 필수" };
      } else if (this.password !== this.password_confirm) {
        this.errors = {
          ...this.errors,
          password_confirm: "비밀번호가 다릅니다",
        };
      }
      // if (!this.errors.length) return true;
    },
  },
};
</script>
<style scoped>
.error-message {
  padding-left: 5px;
  margin-top: 0px;
  font-size: 10px;
  color: red;
  text-align: left;
}
.is-valid {
  flex: 1 1 auto;
  display: block;
  margin-bottom: 10px;
  margin-right: 8px;
  padding: 4px;
  margin-top: -4px;
  width: 60%;
  border: 1px red;
  outline: solid red;
  background: #ffc463;
}
#additional {
  background: #ffffff;
  color: #828282;
  border-bottom: 3px solid #ffc463;
  /* text-decoration: underline #ffc463; */
  border-radius: 0px;
  font-size: 18px;
}
span {
  padding: 8px;
}
.input-button {
  margin-bottom: 10px;
  margin-right: 8px;
  padding: 4px;
  margin-top: -4px;
  width: 60%;
}
.row {
  display: flex;
  flex-direction: row;
}
.row > input,
.row > select {
  flex: 3;
}
.row > button {
  flex: 1;
}
.form-group {
  display: flex;
  flex-direction: column;
  width: 60%;
  margin: 0 auto;
}

.form-group label {
  flex: none;
  display: block;
  /* font-size: 1em; */
  text-align: left;
  padding: 12px;
  padding-left: 4px;
  width: 7em;
  margin-right: 0.5em;
}
.register-page {
  margin: 0;
  background-color: #fff0b1;
}
.login-logo {
  width: 180px;
  padding: 24px;
}
.form {
  z-index: 1;
  background: #ffffff;
  height: 2000px;
  margin: 0px 120px;
  padding: 24px;
  text-align: center;
}
.form input,
.form select {
  outline: 0;
  background: #f2f2f2;
  width: 100%;
  border: 0;
  padding: 12px;
  box-sizing: border-box;
  /* font-size: 12px; */
  border-radius: 5px;
}
.form button {
  text-transform: uppercase;
  outline: 0;
  background: #ffc463;
  border-radius: 5px;
  width: 100%;
  border: 0;
  padding: 12px;
  color: #ffffff;
  /* font-size: 12px; */
  -webkit-transition: all 0.3 ease;
  transition: all 0.3 ease;
  cursor: pointer;
}
</style>
