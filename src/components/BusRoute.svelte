<script lang="ts">

    type Stop = {
        seq: number,
        stop_name: string,
        busstopcode: string,
    }

    export let stops: Stop[] = [];

    const stopsCopy = [...stops]
    const firstStop = stopsCopy.shift();
    const lastStop = stopsCopy.pop();

</script>

<div class="mb-3">
    <div class="p-4">
        <ul class="steps steps-vertical lg:steps-horizontal lg:max-w-2xl lg:space-x-5">
            <li class="step step-primary">{firstStop?.stop_name}</li>
            {#each stopsCopy as stop}
                <li class="step">{stop.stop_name}</li>
            {/each} 
            <li class="step step-primary">{lastStop?.stop_name}</li>
        </ul>
    </div>
</div>

