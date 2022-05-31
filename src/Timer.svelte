<script>
import { createEventDispatcher } from "svelte";
import ProgressBar from "./ProgressBar.svelte";
const totalSeconds = 5;
let secondsLeft = totalSeconds;
let isRunning = false;
$: progress = ((totalSeconds-secondsLeft)/totalSeconds)*100;
const dispatch = createEventDispatcher();
function startTimer(){    
    isRunning = true;
    const timer = setInterval(() => {
    secondsLeft -= 1;
    if(secondsLeft == 0){
        clearInterval(timer);
        isRunning = false;
        secondsLeft = totalSeconds;
        dispatch("end");
    }
}, 1000);

}
</script>

<style>
h2{
    text-align: center;
    margin: 0;
}
.start{
    background-color: brown;
    width: 50%;
    margin-top: 10px;
    margin-bottom: 0px;
}

.start[disabled]{
    background-color: rgb(233, 230, 230);
    cursor: not-allowed;
}
</style>

<div bp="grid">
<h2 bp="offset-5@md 4@md 12@sm">Seconds Left: {secondsLeft}</h2>

</div>

<ProgressBar {progress}/>

<div bp="grid"></div>

<button disabled={isRunning} on:click={startTimer} 
bp="offset-5@md 4@md 12@sm" 
class="start">Start</button>