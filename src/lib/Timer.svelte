<script>
  let time = 0;
  let isRunning = false;

  const timer = () => {
    if (isRunning) return;

    isRunning = true;
    let interval = setInterval(() => {
      if (time <= 0) {
        clearInterval(interval);
        isRunning = false;
        return;
      }
      time = time - 1;
    }, 1000);
  };
</script>

<p>{time}</p>
<input type="number" bind:value={time} />
<button on:click={timer}> Start Timer </button>
