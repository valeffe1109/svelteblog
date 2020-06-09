<script context="module"> 
export async function preload(page){
    return this.fetch('https://blogallelica.herokuapp.com/ghost/api/v2/content/pages/?key=894290040c92bcad78f8477989')
    .then(res=>{
        return res.json();
    })
    .then(data=>{
        const pagename = page.path;
        data.pages = data.pages.filter(i => pagename.includes(i.slug));
        return{pagedata: data.pages[0]}
    })
}
</script>

<script>
   export let pagedata;
</script>

<svelte:head>
<title>{pagedata.title}</title>
</svelte:head>

<div class="content">
<h1>{pagedata.title}</h1>
{@html pagedata.html}
</div>