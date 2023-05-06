<template>
  <main>
    <!-- Carousel -->
    <div class="container-fluid p-0">
      <div id="home-slider" class="carousel carousel-light slide" data-bs-ride="carousel">
        <div class="carousel-indicators">
          <button
            type="button"
            data-bs-target="#home-slider"
            data-bs-slide-to="0"
            class="active"
            aria-current="true"
            aria-label="Slide 1"
          ></button>
          <button
            type="button"
            data-bs-target="#home-slider"
            data-bs-slide-to="1"
            aria-label="Slide 2"
          ></button>
          <button
            type="button"
            data-bs-target="#home-slider"
            data-bs-slide-to="2"
            aria-label="Slide 3"
          ></button>
        </div>
        <div class="carousel-inner">
          <div class="carousel-item active" data-bs-interval="6000">
            <div
              class="d-block w-100 slide-image"
              style="background-image: url('/images/Carousel-item-1.jpg')"
              alt="..."
            ></div>
          </div>
          <div class="carousel-item" data-bs-interval="6000">
            <div
              class="d-block w-100 slide-image"
              style="
                background-image: url('public/images/Carousel-item-2.jpg');
                background-position-y: center;
              "
              alt="..."
            ></div>
          </div>
          <div class="carousel-item">
            <div
              class="d-block w-100 slide-image"
              style="background-image: url('public/images/Carousel-item-3.jpg')"
              alt="..."
            ></div>
          </div>
        </div>
        <button
          class="carousel-control-prev"
          type="button"
          data-bs-target="#home-slider"
          data-bs-slide="prev"
        >
          <span class="carousel-control-prev-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Previous</span>
        </button>
        <button
          class="carousel-control-next"
          type="button"
          data-bs-target="#home-slider"
          data-bs-slide="next"
        >
          <span class="carousel-control-next-icon" aria-hidden="true"></span>
          <span class="visually-hidden">Next</span>
        </button>
      </div>
    </div>
    <!-- Serviços -->
    <div class="container-fluid pt-4 pb-4 text-center text-white services" id="services">
      <h1 class="pb-3 services-title wow">Serviços</h1>
      <div class="card-group wow">
        <div class="card align-items-center wow card-1" id="card-img-1">
          <img src="../../public/images/Weddings.png" class="card-img-top rounded w-50" alt="..." />
          <div class="card-body">
            <h5 class="card-title">Casamentos</h5>
            <p class="card-text">
              Nós sabemos que o seu casamento é um dos dias mais importantes da sua vida. É por isso
              que nos dedicamos a criar doces finos de alta qualidade para tornar o seu grande dia
              ainda mais especial
            </p>
          </div>
        </div>
        <div class="card align-items-center wow card-2" id="card-img-2">
          <img
            src="../../public/images/birthdays.png"
            class="card-img-top rounded w-50"
            alt="..."
          />
          <div class="card-body">
            <h5 class="card-title">Aniversários</h5>
            <p class="card-text">
              Seja um aniversário de 5 anos ou uma festa de 15 anos, nós temos os doces finos que
              você precisa para tornar a sua celebração ainda mais especial. Com uma variedade de
              sabores e designs para escolher, nossos doces são perfeitos para adicionar um toque de
              elegância e sofisticação ao seu evento.
            </p>
          </div>
        </div>
        <div class="card align-items-center wow card-3" id="card-img-3">
          <img src="../../public/images/Events.png" class="card-img-top rounded w-50" alt="..." />
          <div class="card-body">
            <h5 class="card-title">Eventos Corporativos</h5>
            <p class="card-text">
              Nosso serviço de doces finos para eventos corporativos é a escolha perfeita para
              impressionar seus clientes e colaboradores.
            </p>
          </div>
        </div>
      </div>
    </div>
    <!-- Contact -->
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
  </main>
</template>
<style>
#home-slider .slide-image {
  min-height: 80vh;
  background-size: cover;
  background-position: center;
}

#home-slider .carousel-item .carousel-caption {
  position: absolute;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: rgba(0, 0, 0, 0.45);
  color: #fff;
}
.services-title {
  margin-top: 50px;
  margin-bottom: 50px;
  animation: fadeIn;
  animation-duration: 3s;
}
#services {
  background-color: #4c0c0c;
}
main {
  background-color: #e9d3ae;
}

.card-body {
  background-color: #4c0c0c;
}
#card-img-1,
#card-img-2,
#card-img-3 {
  background-color: #4c0c0c;
}
.card {
  border: 0;
  border-width: 0 !important;
}
.card-1 {
  animation: fadeInLeft;
  animation-duration: 2s;
}
.card-2 {
  animation: fadeInUp;
  animation-duration: 2s;
}
.card-3 {
  animation: fadeInRight;
  animation-duration: 2s;
}
.card-group {
  margin-bottom: 150px;
}

.contact-title {
  margin-top: 50px;
  margin-bottom: 50px;
  animation: fadeIn;
  animation-duration: 3s;
}
.contact-info {
  margin-bottom: 50px;
  animation: fadeIn;
  animation-duration: 3s;
}
.contact-info-title {
  margin-bottom: 30px;
  animation: fadeIn;
  animation-duration: 3s;
}
.wpp-button-contact-page {
  margin-top: 30px;
  margin-bottom: 30px;
  animation: fadeIn;
  animation-duration: 3s;
}
.contact-overlay {
  animation: fadeIn;
  animation-duration: 3s;
}
.home-quote {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
  font-size: 150%;
  animation: fadeIn;
  animation-duration: 3s;
}
.h3 {
  font-family: "Gill Sans", "Gill Sans MT", Calibri, "Trebuchet MS", sans-serif;
}
.a-contact {
  text-decoration: none;
  color: black;
}

.maps-card {
  margin-left: 5%;
  margin-right: 5%;
}

@media screen and (max-width: 500px) {
  .services-title {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .card {
    border-top: 0 !important;
    border-right: 0 !important;
    border-left: 0 !important;
    border-radius: 0rem !important;
    margin-top: 50px;
    margin-bottom: 50px;
    animation: fadeIn;
    animation-duration: 3s;
  }
  .card-group {
    margin-bottom: 20px;
  }
  .contact-title {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .contact-info {
    text-align: center;
    margin-top: 0px;
    margin-bottom: 20px;
  }
  .sub-button {
    text-align: center;
    margin-bottom: 0px;
    padding-bottom: 0px;
  }
  .wpp-contact {
    padding-top: 0px;
    margin-top: 0px;
  }
  .wpp-button-contact-page {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .maps-card {
    margin-left: 0%;
    margin-right: 0%;
  }
}
</style>
<script>
import "dayjs/locale/pt-br";
export default {
  data() {
    return {
      name: "",
      email: "",
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
        `📅 *Data prevista:* ${formData.dayDate}\n` +
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
