<script>
  import { user } from './user';

  let username;
  let password;

  function login() {
    user.auth(username, password, ({ err }) => err && alert(err));
  }

  function signup() {
    user.create(username, password, ({ err }) => {
      if (err) {
        alert(err);
      } else {
        login();
      }
    });
  }
</script>

<label for="username">Usuario</label>
<input name="username" bind:value={username} minlength="3" maxlength="16" />

<label for="password">Contraseña</label>
<input name="password" bind:value={password} type="password" />

<button class="login" on:click={login}>Entrar</button>
<button class="login"  on:click={signup}>Inscribirme</button>
<label>Bienvenidos a PainaiApp</label>
<label>Mensajero secreto, se recomiendo operar con navegador TOR o red proxy, red VPN</label>
