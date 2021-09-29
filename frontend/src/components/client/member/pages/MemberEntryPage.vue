<template>
  <div class="member-entry-page">
    <div class="form">
      <img
        class="login-logo"
        src="@/assets/images/JoomakLogo_login.svg"
        alt="JoomakLogo"
      />
      <h1>
        회원가입
      </h1>
      <div class="form-group">
        <label for="id">아이디 </label>
        <div class="row">
          <input type="text" id="id" class="input-control" />
          <button class="input-button">중복 체크</button>
        </div>
      </div>
      <div class="form-group">
        <label for="password">비밀번호 </label>
        <!-- <input type="password" id="password" class="input-control" /> -->
        <input type="text" id="password" class="input-control" />
      </div>
      <div class="form-group">
        <label for="password-confirm">비밀번호 확인</label>
        <!-- <input type="password" id="password-confirm" class="input-control" /> -->
        <input type="text" id="password-confirm" class="input-control" />
      </div>
      <div class="form-group">
        <label for="name">이름 </label>
        <input type="text" id="name" class="input-control" />
      </div>

      <div class="form-group">
        <label for="email">이메일</label>
        <div class="row">
          <input type="text" id="email-front" class="input-control" /><span
            >@ &nbsp;</span
          >
          <!-- <input type="text" id="email-back" class="input-control" /> -->
          <select id="email-back" class="input-control">
            <option value="naver.com">naver.com</option>
            <option value="gmail.com">gmail.com</option>
          </select>

          <button class="input-button">인증 요청</button>
        </div>
      </div>

      <div class="form-group">
        <label for="email-confirm"> </label>
        <div class="row">
          <input type="text" id="email-confirm" class="input-control" />
          <button class="input-button">확인</button>
        </div>
      </div>
      <div class="form-group">
        <label for="phone">휴대폰 번호</label>
        <div class="row">
          <!-- <input type="text" id="phone-front" class="input-control" /> -->
          <select id="phone-front" class="input-control">
            <option value="010">010</option>
          </select>
          <span>- &nbsp;</span>
          <input type="text" id="phone-middle" class="input-control" /><span
            >- &nbsp;</span
          >
          <input type="text" id="phone-back" class="input-control" />
        </div>
      </div>
      <div class="form-group">
        <div class="row">
          <label></label>
          <label></label>
          <label></label>
          <button id="additional">추가 정보</button>
          <label></label>
          <label></label>
          <label></label>
        </div>
      </div>
      <div class="form-group">
        <label for="birth">생년월일</label>
        <div class="row">
          <!-- <input type="text" id="year" class="input-control" /> -->
          <select id="year" class="input-control"></select>
          <span>년 &nbsp;</span>
          <input type="text" id="month" class="input-control" /><span
            >월 &nbsp;</span
          >
          <input type="text" id="day" class="input-control" /><span>일</span>
        </div>
      </div>

      <div class="form-group">
        <label for="nickname">별명</label>
        <input type="text" id="nickname" class="input-control" />
      </div>
      <div class="form-group">
        <label for="sex">성별</label>
        <div class="row">
          <select id="sex" class="input-control">
            <option value="남">남</option>
            <option value="여">여</option>
          </select>
          <label></label>
          <label></label>
          <label></label>
          <label></label>
          <label></label>
        </div>
      </div>

      <div class="form-group">
        <div class="row">
          <label></label>
          <label></label>
          <button class="input-button">확인</button>
          <label></label>
          <label></label>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>
<style scoped>
#additional {
  background: #ffffff;
  color: #828282;
  border-bottom: 3px solid #ffc463;
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
  font-size: 1em;
  text-align: left;
  padding: 12px;
  padding-left: 4px;
  width: 7em;
  margin-right: 0.5em;
}
.member-entry-page {
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
