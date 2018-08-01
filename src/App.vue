<template>
  <div id="app">
    <div class="columns is-multiline">
      <div class="column is-12" id="main-header">
        <h1>Jabar Intelligent Operation Center for Smarter Region</h1>
        <div id="logo"><b>JIOC</b><img src="@/assets/logo_60.png" width="32"></div>
      </div>
      <div class="column is-12" id="top-navigation">
        <div id="top-navigation-selected-region">Provinsi Jawa Barat</div>
        <div id="top-navigation-select-region">
          <span>Select region</span>
          <div class="select is-small">
            <select>
              <option value="">Regency / City</option>
            </select>
          </div>
          <div class="select is-small">
            <select>
              <option value="">Subdistrict</option>
            </select>
          </div>
          <div class="select is-small">
            <select>
              <option value="">Village</option>
            </select>
          </div>
        </div>
      </div>
      <div class="column is-12" id="content">
        <router-view/>
      </div>
    </div>
  </div>
</template>

<style lang="less">
@import url('https://js.arcgis.com/4.8/esri/css/main.css');
@import url('../node_modules/bulma/css/bulma.css');
@import url('./assets/less/app');
</style>
