<script>
import HowTo from "./HowTo.svelte";
import Timer from "./Timer.svelte"
let audio;

function timerEnds(e){
    audio.play()

}
</script>

<style>
h1,h3{
    text-align: center
}
</style>

<h1>Handwashing App</h1>
<div>
<Timer on:end={timerEnds}/>
<HowTo/>
</div>
<h3>
<a href="https://freesound.org/people/metrostock99/sounds/345086/">Sound Source</a>
</h3>

<audio src="sound.wav" bind:this={audio}></audio>