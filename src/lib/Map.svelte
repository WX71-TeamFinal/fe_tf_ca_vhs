<script>
  const fetchImage = (async () => {
    const response = await fetch("http://127.0.0.1:5000/generated_map");
    console.log(response);
    return await response;
  })();
</script>

{#await fetchImage}
  <p>...waiting</p>
{:then data}
  <img src={data.message} alt="Dog image" />
{:catch error}
  <p>An error occurred!</p>
{/await}
