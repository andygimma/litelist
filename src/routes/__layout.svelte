<script>
    import "../app.css";

    import { t, locale, locales } from "../i18n";
    
    // Create a locale specific timestamp
    $: time = new Date().toLocaleDateString($locale, {
      weekday: "long",
      year: "numeric",
      month: "long",
      day: "numeric",
    });
  </script>

<nav>
    <div class="navbar bg-base-100">
        <div class="flex-1">
          <a class="btn btn-ghost normal-case text-xl">Litelist</a>
        </div>
        <div class="flex-none">
          <ul class="menu menu-horizontal p-0">
            <li tabindex="0">
              <a>
                {$t("nav.about")}
                <svg class="fill-current" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 24 24"><path d="M7.41,8.58L12,13.17L16.59,8.58L18,10L12,16L6,10L7.41,8.58Z"/></svg>
              </a>
              <ul class="p-2 bg-base-100">
                <li><a>Who we are</a></li>
                <li><a>What we do</a></li>
              </ul>
            </li>
            <li>
                <a>
                    <select bind:value={$locale}>
                        {#each locales as l}
                        <option value={l}>{l}</option>
                        {/each}
                    </select>
                </a>
            </li>
            <li><a>{$t("nav.login")}</a></li>
          </ul>
        </div>
      </div>
</nav>
<slot />
