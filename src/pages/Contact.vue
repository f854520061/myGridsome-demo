<template>
  <Layout>
    <div data-v-78e0b360="" class="container">
      <div data-v-78e0b360="" class="contact-header">
        <h1 data-v-78e0b360="" class="contact-title">Say hi!</h1>
        <p data-v-78e0b360="">
          Leave me a note with any questions you might have, I'll get back to
          you as soon as possible.
        </p>
      </div>
      <form data-v-78e0b360="" name="contact" class="contact-form">
        <div data-v-78e0b360="" class="sender-info">
          <div data-v-78e0b360="">
            <label data-v-78e0b360="" for="name" class="label">Your name</label
            ><input
              v-model="form.name"
              data-v-78e0b360=""
              type="text"
              name="name"
            />
          </div>
          <div data-v-78e0b360="">
            <label data-v-78e0b360="" for="email" class="label"
              >Your email</label
            ><input
              v-model="form.email"
              data-v-78e0b360=""
              type="email"
              name="email"
            />
          </div>
        </div>
        <div data-v-78e0b360="" class="message">
          <label data-v-78e0b360="" for="message" class="label">Message</label
          ><textarea
            v-model="form.message"
            data-v-78e0b360=""
            name="message"
          ></textarea>
        </div>
        <button data-v-78e0b360="" class="button" @click.prevent="onSubmit">
          Submit form
        </button>
      </form>
    </div>
  </Layout>
</template>

<script>
import axios from "axios";

export default {
  name: "Contact",
  data() {
    return {
      form: {
        name: "",
        email: "",
        message: "",
      },
    };
  },
  methods: {
    async onSubmit() {
      try {
        await axios({
          method: "POST",
          url: GRIDSOME_API_URL + "/contacts",
          data: this.form,
        });
        window.alert('发送成功')
      } catch (err) {
        window.alert('发送失败，请稍后重试')
      }
    },
  },
};
</script>

<style>
</style>