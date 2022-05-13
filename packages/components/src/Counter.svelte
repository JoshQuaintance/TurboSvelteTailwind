<script lang="ts">
  let count = 0;

  function addOneToCount() {
    count++;
  }
</script>

<button
  class="relative inline-flex items-center justify-center p-0.5 mb-2 mr-2 mt-5 overflow-hidden text-sm font-medium text-gray-900 rounded-lg group bg-gradient-to-br from-purple-500 to-pink-500 group-hover:from-purple-500 group-hover:to-pink-500 hover:text-white dark:text-white focus:ring-4 focus:ring-purple-200 dark:focus:ring-purple-800 outline-none"
  on:click={addOneToCount}
>
  <span
    class="relative px-5 py-2.5 transition-all ease-in duration-75 bg-white dark:bg-gray-900 rounded-md group-hover:bg-opacity-0"
  >
    Clicked {count}
    {count > 1 ? "times" : "time"}
  </span>
</button>
