<script>
    import RegisterForm from "$lib/components/RegisterForm.svelte"
    import { onMount } from "svelte"
    import { get } from "svelte/store"
    import { goto } from "$app/navigation"
    import { userStore } from "$lib/stores"

    let useLogin

    $: if (useLogin) goto("/login")

    onMount(() => {
        if (get(userStore)) goto("/login")
    })
</script>

<main class="min-h-screen overflow-y-auto flex items-center justify-center px-4 py-12">
	<RegisterForm bind:useLogin/>
</main>