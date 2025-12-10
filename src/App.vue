<template>
  <v-app>
    <v-app-bar>
      <v-container class="d-flex align-center">
        <v-app-bar-title>番茄鐘</v-app-bar-title>
        <v-btn prepend-icon="mdi-home" to="/">首頁</v-btn>
        <v-btn prepend-icon="mdi-format-list-bulleted" to="/list">事項</v-btn>
        <v-btn prepend-icon="mdi-cog" to="/settings">設定</v-btn>
      </v-container>
    </v-app-bar>
    <v-main>
      <!-- Component 代表目前頁面應該顯示的元件 -->
      <router-view v-slot="{ Component }">
        <!--
          keep-alive 被包住的內容不被銷毀
          include 指定要快取的元件名稱
        -->
        <!-- 動態元件，用 is 定義是什麼元件 -->
        <keep-alive include="HomeView">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
    </v-main>
  </v-app>
</template>

<script setup></script>
