<script>
  import * as tauriApi from '@tauri-apps/api'

  let name = ''
  let greetMsg = ''

  async function greet() {
    console.log('greeting', tauriApi)
    greetMsg = await tauriApi.core.invoke('greet', { name })
    console.log('greetMsg', greetMsg)
  }
</script>

<div>
  <input id="greet-input" placeholder="Enter a name..." bind:value={name} />
  <button onclick={greet}>Greet</button>
  <p>{greetMsg}</p>
</div>
