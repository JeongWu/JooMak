<template>
  <div class="modal">
    <div class="overlay" @click="$emit('close')"></div>
    <div class="modal-card">
      <header class="modal-header">
        <!-- <slot name="header" /> -->
        <h1>아이디 찾기</h1>
        <img
          id="icon_close"
          src="@/assets/images/icon_close.svg"
          alt="icon_close"
          @click="$emit('close')"
        />
      </header>
      <div class="modal-content">
        <form @submit.prevent="onSubmit" method="post">
          <div class="form-group">
            <label for="name">이름 </label>
            <input type="text" id="name" class="input-control" v-model="name" />
            <p></p>
          </div>
          <p class="error-message" v-if="error.name">{{ error.name[0] }}</p>

          <div class="form-group">
            <label for="email">이메일</label>
            <input
              type="text"
              id="email"
              class="input-control"
              v-model="email"
            />
            <button class="input-button">인증 요청</button>
          </div>
          <div class="form-group">
            <label for="authentication">인증 번호 </label>
            <input
              type="authentication"
              id="authentication"
              class="input-control"
              v-model="authentication"
            />
            <p></p>
          </div>

          <div class="form-group">
            <label>&nbsp;</label>
            <button type="submit" id="confirm-button">확인</button>
          </div>
        </form>
      </div>
      <footer class="modal-footer">
        <slot name="footer" />
      </footer>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      error: { name: [] },
    };
  },
  // watch: {
  //   name(val) {
  //     this.error.name = validator.validate("name", val);
  //   },
  // },
  methods: {
    onSubmit() {
      this.error.name = this.validate("name", this.name);
    },
    validate(key, val) {
      const errors = [];
      if (!val) {
        errors.push(`${key} field is required`);
      } else {
        if (val.length < 3) {
          errors.push(`${key} field is required`);
        }
      }
      return errors;
    },
  },
};
</script>

<style scoped>
label {
  width: 80px;
}
.input-button {
  margin-bottom: 10px;
  margin-right: 8px;
  padding: 4px;
  margin-top: -4px;
  width: 60%;
}
.form-group > input {
  flex: 3;
}
.form-group > button,
p {
  flex: 1;
}
.modal,
.overlay {
  width: 100%;
  height: 100%;
  position: fixed;
  left: 0;
  top: 0;
  text-align: center;
  color: #828282;
}
#close-button {
  cursor: pointer;
}
#icon_close {
  height: auto;
  width: 12px;
  position: absolute;
  top: 12px;
  right: 12px;
  color: #828282;
  cursor: pointer;
}

.overlay {
  opacity: 0.5;
  background-color: black;
}

.modal-card {
  position: relative;
  max-width: 50%;
  margin: auto;
  margin-top: 100px;
  padding: 20px;
  background-color: white;
  min-height: 500px;
  z-index: 10;
  opacity: 1;
}
.modal-content {
  margin: 24px;
}
header {
  border-bottom: 2px solid #9e9e9e;
}
footer {
  position: absolute;
  left: 0;
  bottom: 0;
  padding: 12px 0;
  width: 100%;
  /* border-top:1px solid; */
}
</style>
