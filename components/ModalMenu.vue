<template>
  <div id="burger-modal" class="modal">
    <div class="modal-dialog">
      <div class="modal-content">
        <div class="modal-body">
          <img
            src="../src/assets/heroes/Fox/LogoFoxSecond.png"
            alt="fox"
            class="bro"
          />
          <ul class="nav">
            <li>
              <nuxt-link to="/profile" data-bs-dismiss="modal" class="link"
                >Профіль</nuxt-link
              >
            </li>
            <li>
              <nuxt-link to="/categories" data-bs-dismiss="modal" class="link"
                >Пройти тестування</nuxt-link
              >
            </li>
            <li>
              <nuxt-link to="/" data-bs-dismiss="modal" class="link"
                >Порадитись з Бро</nuxt-link
              >
            </li>
            <li>
              <nuxt-link to="/" data-bs-dismiss="modal" class="link"
                >Перевірити номер</nuxt-link
              >
            </li>
            <li>
              <nuxt-link to="/" data-bs-dismiss="modal" class="link"
                >Здати шахрая</nuxt-link
              >
            </li>
            <li>
              <nuxt-link to="/" data-bs-dismiss="modal" class="link"
                >Залишити відгук</nuxt-link
              >
            </li>
          </ul>
          <button class="close-btn" @click="closeModal">
            <img src="../src/assets/nav/close.png" alt="close button" />
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ModalMenu',
  methods: {
    closeModal() {
      this.$emit('close')
    },
  },
}
</script>

<style scoped>
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal-content {
  border-radius: 15px;
  max-width: 425px;
  background-color: var(--primary_color);
  background-image: url('../src/assets/background/forms.svg');
  background-size: cover;
  height: 100vh;
  width: 100vw;
  padding: 60px 0 40px;
  display: flex;
  justify-content: center;
}

.modal-body {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}
.modal-body .bro {
  width: 190px;
  display: block;
  margin: 0 auto;
}

.nav {
  display: block;
  text-align: center;
  margin-top: 20px;
  margin-bottom: 30px;
}

.link {
  text-decoration: none;
  color: var(--white_color);
  display: block;
  font-size: 24px;
  font-style: normal;
  font-weight: 500;
  line-height: 150%;
  margin-top: 10px;
  padding: 2px 12px;
  border-radius: 5px;
}

.link:hover,
.link:active {
  background-color: var(--white_color);
  color: var(--primary_color);
}

.close-btn {
  border: none;
  background-color: transparent;
  display: block;
  margin: 0 auto;
}
</style>

