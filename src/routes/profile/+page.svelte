<script>
    let user = {
        username: 'John Doe',
        email: 'john@example.com'
    };

    const handleLogout = () => {
        // Implement logout logic
        console.log('User logged out');
    };
</script>

<main>
    <h1>Profile</h1>
    <p><strong>Username:</strong> {user.username}</p>
    <p><strong>Email:</strong> {user.email}</p>
    <button on:click={handleLogout}>Logout</button>
</main>

<style>
    main {
        text-align: center;
        margin: 2em;
    }
</style>
