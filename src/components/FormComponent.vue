/* eslint-disable vuejs-accessibility/label-has-for */
<template>
   <div id="app" class="container p-3">
  <h3>VeeValidate 驗證套件</h3>
  <!--  v-slot="{ , values, validate }" -->
  <Form @submit="onSubmit" autocomplete="off" v-slot="{ errors }">
    <div class="mb-3">
      <label for="email" class="form-label">Email</label>
      <Field id="email" type="email" name="email"
               placeholder="請輸入Email"
               class="form-control"
               :class="{'is-invalid': errors['email']}"
               rules="email|required"
               v-model="user.email"></Field>
      <Error-message name="email"  class="invalid-feedback"></Error-message>
    </div>

    <div class="mb-3">
      <label for="name" class="form-label">姓名</label>
      <Field id="name" name="姓名" type="text"
               placeholder="請輸入姓名"
               class="form-control"
               :class="{'is-invalid': errors['姓名']}"
               rules="required"
               v-model="user.name"></Field>
      <Error-message name="姓名"  class="invalid-feedback"></Error-message>
    </div>

    <div class="mb-3">
      <label for="phone" class="form-label">電話</label>
      <Field id="phone" name="電話" type="text"
               placeholder="請輸入電話"
               class="form-control"
               :class="{'is-invalid': errors['電話']}"
               :rules="isPhone"
               v-model="user.phone"></Field>
      <Error-message name="電話"  class="invalid-feedback"></Error-message>
    </div>

    <div class="mb-3">
      <label for="region" class="form-label">地區</label>
      <Field id="region" name="地區"
               class="form-control"
               :class="{'is-invalid': errors['地區']}"
               rules="required"
               v-model="user.region"
               as="select">
        <option value="" hidden>請選擇地區</option>
        <option value="台北市">台北市</option>
        <option value="高雄市">高雄市</option>
      </Field>
      <Error-message name="地區"  class="invalid-feedback"></Error-message>
    </div>

    <div class="mb-3">
      <label for="address" class="form-label">地址</label>
      <Field id="address" name="地址" type="text"
               placeholder="請輸入地址"
               class="form-control"
               :class="{'is-invalid': errors['地址']}"
               rules="required"
               v-model="user.address"></Field>
      <Error-message name="地址"  class="invalid-feedback"></Error-message>
    </div>

    <button class="btn btn-primary" type="submit" >Submit</button>
  </Form>
</div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        email: '',
        name: '',
        phone: '',
        region: '',
        address: '',
      },
    };
  },

  methods: {
    onSubmit(value, { resetForm }) {
      this.card = JSON.parse(JSON.stringify(value));
      resetForm();
    },
    isPhone(value) {
      // eslint-disable-next-line prefer-regex-literals
      const phoneReg = new RegExp('^(09)[0-9]{8}$');
      return !value.match(phoneReg) ? '電話格式錯誤' : true;
    },
  },
};
</script>
