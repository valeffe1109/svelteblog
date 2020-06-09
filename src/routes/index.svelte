<script context="module">
    export async function preload(page){
     console.log(page)
     return this.redirect(302, 'home');
    }
</script>