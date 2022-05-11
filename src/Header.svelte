<script>
  import { username, user } from './user';

  function signout() {
    user.leave();
    username.set('');
  }
</script>

<header>
<h1>PainaiApp</h1>
  {#if $username}
    <div class="user-bio">
      
      <span>Hola<strong>{$username}</strong></span>
      <img src={`https://avatars.dicebear.com/api/initials/${$username}.svg`} alt="avatar" /> 
    </div>

    <button class="signout-button" on:click={signout}>Salir</button>

    {:else}

      <h3>UAEH</h3>
  {/if}
</header>