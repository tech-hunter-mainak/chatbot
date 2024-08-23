<script>
    /**
	 * @type {any[]}
	 */
    let messages = [];
    let userMessage = '';

    const sendMessage = () => {
        if (userMessage.trim()) {
            messages = [...messages, { text: userMessage, sender: 'user' }];
            userMessage = '';

            // Simulate a bot response
            setTimeout(() => {
                messages = [...messages, { text: "This is a bot response.", sender: 'bot' }];
            }, 500);
        }
    };
</script>

<main>
    <h1>Chatbot</h1>
    <div class="chat-window">
        {#each messages as message}
            <div class="{message.sender}">
                {message.sender === 'user' ? 'You: ' : 'Bot: '}{message.text}
            </div>
        {/each}
    </div>
    <input type="text" bind:value={userMessage} placeholder="Type a message..." on:keypress="{e => e.key === 'Enter' && sendMessage()}" />
    <button on:click={sendMessage}>Send</button>
</main>

<style>
    .chat-window {
        border: 1px solid #ccc;
        padding: 1em;
        height: 300px;
        overflow-y: auto;
        margin-bottom: 1em;
    }
    .user {
        text-align: right;
        color: blue;
    }
    .bot {
        text-align: left;
        color: green;
    }
    input {
        width: 80%;
        padding: 0.5em;
        margin-right: 1em;
    }
</style>
