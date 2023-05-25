<script context="module" lang="ts">
    export const prerender = true;
</script>
  
<script>
    import { onMount } from "svelte";
    let played = false;

    onMount(async () => {
        await import("@mux/mux-player");
    });

</script>
  
<mux-player
    playback-id="g65IqSFtWdpGR100c2W8VUHrfIVWTNRen"
    metadata-video-id="54322"
    metadata-video-title="Test"
    metadata-viewer-user-id="me"
    stream-type="on-demand"
    thumbnail-time="9"
    on:play|once="{() => played = true}"
    class:played
    
/>

<style>

.played {
    --bottom-controls: unset;
    --cast-button: none;
    --pip-button: none;
    --playback-rate-button: none;
}
    
mux-player {
    width: 100%;
    max-width: 800px;
    margin: 20px auto;

    --seek-backward-button: none;
    --seek-forward-button: none;
    --bottom-controls: none;
    --cast-button: none;
    --pip-button: none;
    --playback-rate-button: none;
}

</style>