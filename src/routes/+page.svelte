<!-- <h1>Welcome to SvelteKit</h1> -->
<!-- <p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p> -->
<script>
  let name = $state('');
  let welcome = $derived(name ? 'Hello, ${name}!' : 'Welcome!');

  function randomize() {
    const msgs =['웹 개발 재밌다!', 'SvelteKit 금방 익힘', 'Vercel 배포도 쉽다!'];
    alert(msgs[Math.floor(Math.random() * msgs.length)]);

  }
</script>

<h1>{welcome}</h1>

<label>
  Your name: <input placeholder="type your name" bind:value={name} />
</label>
<p>미리보기: <strong>{name || '(입력대기)' }</strong></p>

<button onclick={randomize}>랜덤 메세지</button>