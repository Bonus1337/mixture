<template>

  <div class="fog">

    <div class="modal">

      <header>

        <h1>

          <slot name="header" />

        </h1>

      </header>

      <div class="modal__body">

        <slot name="body" />

      </div>

      <footer>

        <slot name="footer" />

        <button-item
          :movement="0"
          @click="$emit('cancel')"
          icon="pi pi-times"
        />

      </footer>

    </div>

  </div>

</template>

<script>
import ButtonItem from "./ButtonItem";
export default {
  name: "ModalItem",
  components: { ButtonItem }
};
</script>

<style lang="scss" scoped>
@import "@/styles/variables";
.fog {
  @include width-height-100;
  @include top-left-0;
  background-color: #21d4fd;
  background-image: linear-gradient(19deg, #21d4fd 0%, #b721ff 100%);
  position: fixed;
  display: flex;
  z-index: 2;
}
.modal {
  max-width: 20rem;
  padding: 20px;
  background: #fff;
  margin: auto auto;
  border-radius: 2rem;
  box-shadow: 0 0 20px 20px rgba(0, 0, 0, 0.1);
  color: #637892;
  &__body {
    font-size: 1rem;
    margin-bottom: 2rem;
  }
}
</style>

