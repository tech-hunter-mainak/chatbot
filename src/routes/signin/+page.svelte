<script>
    let username = '';
    let password = '';
    let isSignup = false;

    const handleSubmit = () => {
        console.log(`${isSignup ? 'Signup' : 'Signin'} with`, { username, password });
    };
</script>

<main>
    <h1>{isSignup ? 'Signup' : 'Signin'}</h1>
    <form on:submit|preventDefault={handleSubmit}>
        <input type="text" bind:value={username} placeholder="Username" required />
        <input type="password" bind:value={password} placeholder="Password" required />
        <button type="submit">{isSignup ? 'Signup' : 'Signin'}</button>
    </form>
    <button on:click={() => isSignup = !isSignup}>
        {isSignup ? 'Already have an account? Signin' : 'New here? Signup'}
    </button>
</main>

<style>
    main {
        text-align: center;
        margin: 2em;
    }
    input {
        display: block;
        margin: 1em auto;
    }
</style>
