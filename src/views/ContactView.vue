<template>
  <div id="contact-page">
    <div class="container text-center pt-4 contact-info-p4">
      <h2>Informações de Contato</h2>
      <p class="pt-3">
        <a href="https://www.instagram.com/tiene_doces_finos/" target="_blank" class="a-contact">
          <i class="bi bi-instagram"></i>
          Tiene doces finos
        </a>
      </p>
      <p>
        <a href="https://wa.me/+554497602781" target="_blank" class="a-contact">
          <i class="bi bi-whatsapp ps-2"></i> (44) 9760-2781
        </a>
      </p>
      <p>
        <a href="https://goo.gl/maps/zrhweMRNuy3LYc4w6" target="_blank" class="a-contact">
          <i class="bi bi-geo-alt ps-2"></i>
          Rua Alexandra, 521
        </a>
      </p>
    </div>
    <div class="container py-0 mt-4 contact-overlay">
      <div class="row">
        <div class="col-12 col-lg-6 mb-4">
          <form @submit="submitForm($event)">
            <div class="row justify-content-center mb-3">
              <div class="col-12">
                <label for="formGroupExampleInput" class="form-label">Nome</label>
                <input
                  type="text"
                  class="form-control"
                  id="formGroupExampleInput"
                  placeholder="Digite seu nome"
                  v-model="name"
                  :disabled="sendingForm"
                />
              </div>
            </div>
            <div class="row justify-content-center mb-3">
              <div class="col-12">
                <label for="phone" class="form-label">Telefone</label>
                <input
                  type="text"
                  class="form-control"
                  id="phone"
                  name="phone"
                  placeholder="(xx) xxxxx-xxxx"
                  v-model="phone"
                  @keypress="phoneMask($event)"
                  :disabled="sendingForm"
                />
              </div>
            </div>
            <div class="row justify-content-center mb-3">
              <div class="col-12">
                <label for="Date" class="form-label">Data Prevista</label>
                <input
                  type="text"
                  name="date"
                  class="form-control"
                  id="Date"
                  placeholder="DD/MM/AAAA"
                  v-model="dayDate"
                  :disabled="sendingForm"
                />
              </div>
            </div>
            <div class="row justify-content-center mb-3">
              <div class="col-12">
                <label for="exampleFormControlTextarea1" class="form-label"
                  >Digite sua mensagem:
                </label>
                <textarea
                  class="form-control"
                  id="exampleFormControlTextarea1"
                  rows="6"
                  v-model="msg"
                  :disabled="sendingForm"
                ></textarea>
              </div>
            </div>
            <div class="row justify-content-center mb-3">
              <div class="col-12">
                <p v-if="formError" class="text-danger">{{ formError }}</p>
                <p v-if="formSent" class="text-success">
                  Recebemos a sua mensagem. Responderemos em breve! 😉
                </p>
                <div class="sub-button-p4">
                  <button
                    type="submit"
                    class="btn btn-primary submit-button mt-2 btn-lg w-50"
                    :disabled="sendingForm"
                  >
                    <span
                      v-if="sendingForm"
                      class="spinner-border spinner-border-sm me-2"
                      role="status"
                      aria-hidden="true"
                    ></span>

                    <span v-if="sendingForm">Enviando...</span>
                    <span v-if="!sendingForm">Enviar</span>
                  </button>
                </div>
              </div>
            </div>
          </form>
        </div>
        <div class="col-12 col-lg-6 mb-4 badge text-wrap justify-content-center">
          <div class="text-center fs-3 pt-3 text-dark">Entre em contato através do WhatsApp:</div>
          <div class="pt-2">
            <a href="https://wa.me/+554497602781" target="_blank" rel="noopener noreferrer">
              <button type="button" class="btn btn-success wpp-button-contact-page">
                <i class="bi bi-whatsapp"></i> (44) 9760-2781
              </button></a
            >
          </div>
          <div class="pt-2 maps-card-p4">
            <iframe
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3661.3156123207573!2d-51.90257308255615!3d-23.412963499999993!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x94ecd0fbd2265117%3A0x3a2b5e17f33c7c8b!2sR.%20Alexandra%2C%20521%20-%20Parque%20Res.%20Patricia%2C%20Maring%C3%A1%20-%20PR%2C%2087040-460!5e0!3m2!1spt-BR!2sbr!4v1683075889852!5m2!1spt-BR!2sbr"
              width="100%"
              height="350"
              style="border: 0; border-radius: 1rem"
              allowfullscreen=""
              loading="lazy"
              referrerpolicy="no-referrer-when-downgrade"
            ></iframe>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<style>
.submit-button {
  width: auto;
  margin-left: auto;
  margin-right: auto;
  display: block;
}

#contact-page {
  background-color: #e9d3ae;
}
.contact-info-p4 {
  animation: fadeIn;
  animation-duration: 3s;
}
@media screen and (max-width: 500px) {
  .sub-button-p4 {
    text-align: center;
  }
  .contact-info-p4 {
    text-align: center;
  }
}
</style>
<script>
export default {
  data() {
    return {
      name: "",
      dayDate: "",
      phone: "",
      msg: "",
      formError: "",
      sendingForm: false,
      formSent: false
    };
  },

  methods: {
    phoneMask(event) {
      event.preventDefault();

      const key = event.key;
      if (!key || isNaN(Number(key))) {
        return;
      }

      this.phone = this.phone + key;

      let phoneNumber = this.phone.replace(/\D/g, "");
      let formattedPhone = "";

      if (phoneNumber.length < 1) {
        formattedPhone = "";
      } else if (phoneNumber.length < 3) {
        formattedPhone = "(" + phoneNumber;
      } else if (phoneNumber.length < 7) {
        formattedPhone = "(" + phoneNumber.substring(0, 2) + ") " + phoneNumber.substring(2);
      } else if (phoneNumber.length < 11) {
        formattedPhone =
          "(" +
          phoneNumber.substring(0, 2) +
          ") " +
          phoneNumber.substring(2, 6) +
          "-" +
          phoneNumber.substring(6);
      } else {
        formattedPhone =
          "(" +
          phoneNumber.substring(0, 2) +
          ") " +
          phoneNumber.substring(2, 7) +
          "-" +
          phoneNumber.substring(7);
      }

      this.phone = formattedPhone.substring(0, 15);
    },

    submitForm(event) {
      event.preventDefault();

      if (this.sendingForm) return;

      this.formError = "";
      this.formSent = false;

      if (this.name.length <= 0) {
        this.formError = "O nome é obrigatório";
        return;
      }

      if (this.phone.length <= 0) {
        this.formError = "O telefone é obrigatório";
        return;
      }

      if (this.dayDate.length <= 0) {
        this.formError = "A data prevista é obrigatória";
        return;
      }

      if (this.msg.length <= 0) {
        this.formError = "A mensagem é obrigatória";
        return;
      }

      this.sendingForm = true;

      const formData = {
        name: this.name,
        dayDate: this.dayDate,
        phone: this.phone,
        message: this.msg
      };

      const whatsText =
        `*Olá! Gostaria de entrar em contato com você.*\n` +
        `\n` +
        `🪪 *Nome:* ${formData.name}\n` +
        `\n` +
        `*Data prevista:* ${formData.dayDate}\n` +
        `\n` +
        `📄 *Mensagem:*\n` +
        `${formData.message}`;

      window.open(
        `https://api.whatsapp.com/send/?phone=554497602781&text=${encodeURI(
          whatsText
        )}&type=phone_number&app_absent=0`,
        "_blank"
      );

      setTimeout(() => {
        console.log("Form submitted", formData);

        this.formSent = true;

        this.name = "";
        this.phone = "";
        this.dayDate = "";
        this.msg = "";

        this.sendingForm = false;
      }, 0);
    }
  }
};
</script>
