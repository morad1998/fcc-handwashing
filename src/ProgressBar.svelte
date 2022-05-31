<script>
    export let progress = 0;
</script>

<style>
.progress-container{    
    width: 50%;
    margin-top: 20px;
    margin-bottom: 0px;
    border: solid peru 1px;
}
.progress-bar{
    
    height: 30px;
    background-color: aqua;
}


</style>


<div bp="grid">
    <div class="progress-container">
        <div class="progress-bar"  style="width: {progress}%;">
            <span  class="sr-only">{progress}%</span>
        </div>
    </div>
</div>
