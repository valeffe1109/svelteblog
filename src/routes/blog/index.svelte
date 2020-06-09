<script context="module">
  export async function preload(page) {
    return this.fetch(
      "https://blogallelica.herokuapp.com/ghost/api/v2/content/posts/?key=894290040c92bcad78f8477989"
    )
      .then(res => {
        return res.json();
      })
      .then(data => {
        return { posts: data.posts };
      });
  }
</script>

<script>
  export let posts;
</script>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<ul>
{#each posts as post}
  <li><a rel="prefetch" href="blog/{post.slug}">{post.title}</a></li>
{/each}
</ul>
