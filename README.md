import random
import time

# -------------------------------
# Virtual Chat Arena - Python Project
# -------------------------------

class ChatBot:
    def __init__(self, name, responses):
        self.name = name
        self.responses = responses

    def reply(self, message):
        """
        Generate a reply based on the incoming message.
        For simplicity, selects a random response from its list.
        """
        response = random.choice(self.responses)
        return f"{self.name}: {response}"


def main():
    # Define the bots and their response lists
    bot1 = ChatBot("Bot Alpha", [
        "Hello there!",
        "How are you today?",
        "I enjoy chatting!",
        "That's interesting.",
        "Tell me more!"
    ])

    bot2 = ChatBot("Bot Beta", [
        "Hi! Nice to meet you.",
        "I'm doing well, thanks!",
        "Wow, really?",
        "That sounds fascinating!",
        "Can you explain more?"
    ])

    # Starting message
    message = "start"
    print("=== Welcome to Virtual Chat Arena ===\n")

    # Chat loop (10 exchanges)
    for i in range(10):
        message = bot1.reply(message)
        print(message)
        time.sleep(1)  # pause to simulate typing
        message = bot2.reply(message)
        print(message)
        time.sleep(1)

    print("\n=== End of Virtual Chat Arena ===")

if __name__ == "__main__":
    main()
