<script lang="ts">
    import { onMount } from "svelte"
    import { getName, getVersion } from "@tauri-apps/api/app"

    type App = {
        name: string
        version: string
    }

    let app: App = { name: "", version: "" }
    onMount(async (): Promise<void> => {
        app.name = await getName()
        app.version = await getVersion()
    })
</script>

<div>{app.name}</div>
<div>Version: {app.version}</div>
