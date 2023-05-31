<template>
  <footer class="mt-auto">
    <div class="footer-content">
      <h3>Tiene Doces Finos</h3>
      <p>Doces para seu evento</p>
    </div>
    <div>
      <ul class="socials">
        <li>
          <a href="https://www.instagram.com/tiene_doces_finos/" target="_blank"
            ><i class="bi bi-instagram"></i
          ></a>
        </li>
        <li>
          <a href="https://wa.me/+554497602781" target="_blank"> <i class="bi bi-whatsapp"></i></a>
        </li>
      </ul>
    </div>
    <div class="footer-menu">
      <ul class="f-menu">
        <li><router-link class="nav-link" to="/">Início</router-link></li>
        <li><router-link class="nav-link" to="/servicos">Serviços</router-link></li>
        <li><router-link class="nav-link" to="/contato">Contato</router-link></li>
      </ul>
    </div>
    <br />
    <div class="footer-bottom">
      <p>
        © 2023 Tiene Doces Finos - Todos os direitos reservados | Desenvolvido por
        <a href="https://github.com/DioneyJunior" target="_blank">Dioney Junior</a>
      </p>
    </div>
  </footer>
</template>
<script>
export default {
  name: "FooterSite"
};
</script>
<style>
footer {
  background-color: #4c0c0c;
  bottom: 0;
  left: 0;
  right: 0;
  height: auto;
  padding-top: 40px;
  color: #ce9e60;
}
.footer-content {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  text-align: center;
  margin: 10px;
}
.footer-content h3 {
  color: #ce9e60;
  font-size: 2.1rem;
  font-weight: 500;
  text-transform: capitalize;
  margin-bottom: 5px;
}
.footer-content p {
  margin: 5px;
}
.socials {
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: center;
  padding-left: 0;
}
.socials li {
  margin: 0 10px;
}

.socials a {
  text-decoration: none;
  color: #ce9e60;
  padding: 5px;
}
.socials a i {
  font-size: 1.1rem;
  width: 20px;
  transition: color 0.4s ease;
}
.socials a:hover i {
  color: #e99f3e;
}
.footer-bottom {
  background: #3b0a0a;
  padding: 10px;
  text-align: center;
}
.footer-bottom p {
  font-size: 14px;
  word-spacing: 2px;
  text-transform: capitalize;
}
.footer-bottom p a {
  color: #e99f3e;
  font-size: 16px;
  text-decoration: none;
}
.footer-bottom span {
  text-transform: uppercase;
  opacity: 0.4;
  font-weight: 200;
}

.footer-menu ul {
  display: flex;
  padding-left: 0;
  margin-bottom: 0;
  justify-content: center;
}

.footer-menu ul li {
  padding-right: 10px;
  display: block;
}

.footer-menu ul li a {
  color: #ce9e60;
  text-decoration: none;
}

.footer-menu ul li a:hover {
  color: #e99f3e;
}
</style>
