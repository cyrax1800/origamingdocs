<template>
  <section class="section">
    <div class="columns">
      <div class="column is-2">
        <div class="field is-grouped">
          <p class="control is-expanded has-icons-left">
            <input class="input" type="text" placeholder="Search">
            <span class="icon is-small is-left">
              <i class="fa fa-search"></i>
            </span>
          </p>
        </div>

        <aside class="menu">
          <p class="menu-label">
            Script
          </p>
          <ul class="menu-list">
            <li>
              <nuxt-link to="/docs/enums">Enums</nuxt-link>
              <nuxt-link to="/docs/core">Core</nuxt-link>
              <nuxt-link to="/docs/utilities">Utilities</nuxt-link>
              <ul>
                <li>
                  <nuxt-link to="/docs/member">Member</nuxt-link>
                </li>
              </ul>
            </li>
          </ul>
          <p class="menu-label">
            GameObject / Prefabs
          </p>
          <ul class="menu-list">
            <li>
              <nuxt-link to="/docs/debug_panel">Debug Panel</nuxt-link>
            </li>
          </ul>
        </aside>

      </div>
      <div class="column is-10">
        <nuxt/>
      </div>
    </div>
  </section>
</template>

<style>

</style>
