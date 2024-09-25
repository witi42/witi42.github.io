---
layout: default
---
# Robin Wiethüchter
Hi 👋, I’m Robin, software engineer and co-founder of [Clipmate AI](https://clipmate.ai/).

I've studied computer science at ETH Zürich (BSc, MSc) and previously worked at [urb-x AG](https://urb-x.ch/).

Alongside my main work, I've enjoyed teaching CS at Zurich International School and LernCenter for [Hebbian](https://hebbian.ch/).


For work and project opportunities, hit me up on [LinkedIn](https://www.linkedin.com/in/robin-wiethuchter/) or reach out to <img src="{{ site.url | default: rowi.dev }}{{ site.baseurl }}/assets/images/hi.jpeg" aria-hidden="true" style="height: 1.8em; vertical-align: text-bottom; margin: 0 0.2em; display: inline-block;">

<!-- > [LinkedIn](https://www.linkedin.com/in/robin-wiethuchter/) [X](https://x.com/wiethix) -->


## Ask me Anything - Chatbot
<div id="chatbot" style="border: 1px solid #ccc; padding: 10px; max-width: 500px;">
    <div id="chat-history" style="height: 140px; overflow-y: auto; border-bottom: 1px solid #ccc; margin-bottom: 10px;">
        <!-- Chat history will be appended here -->
    </div>
    <input type="text" id="user-input" placeholder="Type a message" style="width: 70%; padding: 5px;"/>
    <button id="send-btn" style="margin-top: 5px; width: 100px; padding: 5px;">Send</button>
</div>

<script>
    const chatHistory = [];

    async function sendMessage() {
        const userMessage = document.getElementById('user-input').value;
        if (!userMessage) return;

        chatHistory.push(`You: ${userMessage}`);
        updateChatHistory();

        document.getElementById('user-input').value = '';  // Clear input

        const response = await fetch('https://europe-west6-experiments-425922.cloudfunctions.net/chatbot', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({ 
                userMessage: userMessage, 
                chatHistory: chatHistory.join('\n') 
            })
        });

        const data = await response.json();
        chatHistory.push(`Robin Bot: ${data.message}`);
        updateChatHistory();
    }

    document.getElementById('send-btn').addEventListener('click', sendMessage);

    document.getElementById('user-input').addEventListener('keypress', function(event) {
        if (event.key === 'Enter') {
            sendMessage();
        }
    });

    function updateChatHistory() {
        const chatHistoryElem = document.getElementById('chat-history');
        if (chatHistory.length === 0) {
            chatHistoryElem.innerHTML = `
                <p>Things you could ask:</p>
                <p>- How can I contact you?</p>
                <p>- How good are you with python?</p>
            `;
        } else {
            chatHistoryElem.innerHTML = chatHistory.map(msg => `<p>${msg}</p>`).join('');
        }
        chatHistoryElem.scrollTop = chatHistoryElem.scrollHeight;  // Scroll to the bottom
    }

    // Initialize chat history with demo questions
    updateChatHistory();
</script>


## Projects

{% for post in site.posts %}
<!-- - [{{ post.title }} >>]({{ post.url }}) _{{ post.date | date: "%B %d, %Y" }}_ -->
- **{{ post.title }}** - _{{ post.date | date: "%B %d, %Y" }}_

    {{ post.excerpt }}

    {% if post.image %}
    <img src="{{ site.url | default: rowi.dev }}{{ site.baseurl }}/assets/images/{{ post.image }}" alt="{{ post.image_alt }}" width="280" style="display: block; margin-left: 0;">
    {% endif %}

    {% if post.youtube %}
    <div class="video-container">
        <iframe width="280" height="157" src="https://www.youtube.com/embed/{{ post.youtube | split: '/' | last }}" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
    {% endif %}

    [more ...]({{ post.url }})
{% endfor %}


