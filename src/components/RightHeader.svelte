<script>
  import { _, locales, locale as currentLocale } from "svelte-i18n";
</script>

<nav class="navbar navbar-expand text-primary mt-3 mr-2">
  <div class="container-fluid">
    <ul class="ml-auto navbar-nav">
      <li class="nav-item dropdown">
        <a
          class="nav-link text-primary"
          href="#"
          id="navbarDropdown"
          role="button"
          data-toggle="dropdown"
          aria-haspopup="true"
          aria-expanded="false"
        >
          {$_('language-name')}
          <i class="fas fa-angle-down"></i>
        </a>
        <div class="dropdown-menu" aria-labelledby="navbarDropdown">
          {#each $locales as locale}
            <a
              class="dropdown-item text-primary"
              href="javascript:void(0);"
              class:font-weight-bold="{$currentLocale
                .toLowerCase()
                .startsWith(locale)}"
              on:click="{() => currentLocale.set(locale)}"
            >{$_('language-name', { locale })}</a>
          {/each}
        </div>
      </li>
      <li class="nav-item mx-4">
        <a href="/login" class="btn btn-primary d-flex align-items-center"><i
            class="far fa-user fa-xs mr-2"
          ></i>
          Login
          <i class="fas fa-chevron-right fa-xs ml-2"></i>
        </a>
      </li>
    </ul>
  </div>
</nav>
