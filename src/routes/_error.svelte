<script>
  export let status
  export let error
</script>

<style>
  @media only screen and (max-width: 1023px) {
    article {
      width: 90%;
      margin: 10px auto;
    }
  }

  @media only screen and (min-width: 1024px) {
    article {
      width: 50%;
      margin: 50px auto;
    }
  }
  
</style>

<svelte:head>
  <title>Error: {status}</title>
</svelte:head>

<article class="message is-warning">
  <div class="message-header">
    <p>Oops! {status}</p>
  </div>
  <div class="message-body">
    {#if status === 404}
      <p>
        It looks like the page you're after doesn't exist. Maybe it's moved, or
        maybe the author of the site made a typo? Not sure, but it's not here
        now.
      </p>
    {:else if status === 403}
      <p>It looks like you're not allowed access to that page.</p>
    {:else if status === 500}
      <p>
        It looks like there's been a problem on the other end. You could try
        loading again, maybe?
      </p>
    {:else if status === 503}
      <p>
        It looks like the site is currently unavailable. It might be down for
        maintenance or overloaded. Try again soon.
      </p>
    {:else if status === 504}
      <p>
        It looks like the site is was too slow to respond. It could be busy or
        overloaded. Try again soon.
      </p>
    {:else}
      <p>
        The servers are telling us that there's been a
        <strong>{status}</strong>
        error, which apparently means "{error.message}".
      </p>
    {/if}
		<br>
    <p>Would you like to go <a href=".">home</a>?</p>
  </div>
</article>
