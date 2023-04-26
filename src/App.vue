<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <nav class="navbar navbar-expand-lg bg-body-tertiary">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">
        <img
          alt="Vue logo"
          class="logo"
          src="@/assets/chat/img/logo.png"
          width="64"
          height="64"
      /></a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mx-auto mb-2 mb-lg-0">
          <li class="nav-item">
            <RouterLink class="nav-link" to="/">صفحه اصلی </RouterLink>
          </li>

          <li class="nav-item">
            <RouterLink class="nav-link" to="/chat">چت </RouterLink>
          </li>
        </ul>
        <ul class="d-flex navbar-nav">
          <li class="nav-item">
            <RouterLink class="nav-link" to="/login">ورود</RouterLink>
          </li>
          <li class="nav-item">
            <RouterLink class="nav-link" to="/register">ثبت نام </RouterLink>
          </li>
        </ul>
      </div>
    </div>
  </nav>

  <RouterView />
</template>

<style scoped>
</style>
