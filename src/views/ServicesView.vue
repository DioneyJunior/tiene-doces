<template>
  <div class="container-fluid pt-4 pb-4 text-center" id="template">
    <h1 class="pb-3 services-title-p3">Serviços</h1>
    <div class="card-group">
      <div class="card align-items-center animate__animated animate__fadeInUp" id="card-img1">
        <img src="/images/birthdays.png" class="card-img-top w-50" alt="..." />
        <div class="card-body" id="card-text-1">
          <h5 class="card-title">Casamentos</h5>
          <p class="card-text">
            Nós sabemos que o seu casamento é um dos dias mais importantes da sua vida. É por isso
            que nos dedicamos a criar doces finos de alta qualidade para tornar o seu grande dia
            ainda mais especial.
          </p>
        </div>
      </div>
      <div
        class="card align-items-center animate__animated animate__fadeInUp animate__delay-1s"
        id="card-img2"
      >
        <img src="/images/Weddings.png" class="card-img-top w-50" alt="..." />
        <div class="card-body" id="card-text-2">
          <h5 class="card-title">Aniversários</h5>
          <p class="card-text">
            Seja um aniversário de 5 anos ou uma festa de 15 anos, nós temos os doces finos que você
            precisa para tornar a sua celebração ainda mais especial. Com uma variedade de sabores e
            designs para escolher, nossos doces são perfeitos para adicionar um toque de elegância e
            sofisticação ao seu evento.
          </p>
        </div>
      </div>
      <div
        class="card align-items-center animate__animated animate__fadeInUp animate__delay-2s"
        id="card-img3"
      >
        <img src="/images/Events.png" class="card-img-top w-50" alt="..." />
        <div class="card-body" id="card-text-3">
          <h5 class="card-title">Eventos corporativos</h5>
          <p class="card-text">
            Nosso serviço de doces finos para eventos corporativos é a escolha perfeita para
            impressionar seus clientes e colaboradores.
          </p>
        </div>
      </div>
    </div>
  </div>
</template>
<style services-page>
#template {
  background-color: #e9d3ae;
}
.services {
  background-color: #e9d3ae;
}

#card-text-1,
#card-text-2,
#card-text-3 {
  background-color: #e9d3ae;
}
#card-img1,
#card-img2,
#card-img3 {
  background-color: #e9d3ae;
}
.services-title-p3 {
  margin-top: 30px;
  margin-bottom: 30px;
  animation: fadeInDown;
  animation-duration: 3s;
}
.card-title {
  margin-top: 30px;
}
.card-text {
  margin-top: 20px;
}
</style>
<script></script>
