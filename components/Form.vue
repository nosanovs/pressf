<template>
    <div class="form">
        <form action="#">
            <div class="form__item">
                <label
                    class="form__label"
                    for="email"
                >
                    Email:
                </label>
                <input
                    type="text"
                    id="email"
                    name="email"
                    placeholder="Email"
                    class="form__input form__input--text"
                >
            </div>
            <div class="form__item">
                <label
                    class="form__label"
                    for="password"
                >
                    Пароль:
                </label>
                <input
                    type="text"
                    id="password"
                    name="password"
                    placeholder="Пароль"
                    class="form__input form__input--text"
                >
            </div>
            <div
                v-if="isRegistered"
                class="form__row"
            >
                <div>
                    <input
                        type="checkbox"
                        id="remember"
                        class="form__input form__input--checkbox"
                    >
                    <label for="remember">Запомнить меня</label>
                </div>
                <a href="#">Забыли пароль?</a>
            </div>
            <button
                v-if="isRegistered"
                @click="onLoginClick"
                type="button"
                class="form__action form-action"
            >
                <span class="form-action__text">Войти</span>
            </button>
            <button
                v-else
                @click="onRegistrationClick"
                type="button"
                class="form__action form-action"
            >
                <span class="form-action__text">Зарегистрироваться</span>
            </button>
        </form>
    </div>
</template>

<script lang="ts">
    export default {
        props: {
            isRegistered: {
                type: Boolean,
                default: false,
            },
        }
    }
</script>

<style lang="scss" scoped>
  @use "./styles/form/form";
</style>
