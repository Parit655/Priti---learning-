# Priti---learning-
This is my first repository.
<br>
Author-priti kumari 
my first project python 
# WhatsApp-Style Chat App (Text-Based Simulator)
users = {}
messages = {}

def register():
    username = input("Enter your name to register: ")
    if username in users:
        print("Username already exists!")
    else:
        users[username] = True
        messages[username] = []
        print(f"{username} registered successfully!")

def send_message():
    sender = input("Enter your name: ")
    if sender not in users:
        print("User not found! Please register first.")
        return
    receiver = input("Enter receiver's name: ")
    if receiver not in users:
        print("Receiver not found!")
        return
    message = input("Type your message: ")
    messages[receiver].append(f"{sender}: {message}")
    print("Message sent successfully!")

def view_messages():
    username = input("Enter your name to view messages: ")
    if username not in users:
        print("User not found!")
    else:
        print("\nYour Messages:")
        for msg in messages[username]:
            print(msg)
        print("End of messages.\n")

# Main Loop
while True:
    print("\n--- WhatsApp Chat App ---")
    print("1. Register")
    print("2. Send Message")
    print("3. View Messages")
    print("4. Exit")
    choice = input("Choose an option (1-4): ")

    if choice == "1":
        register()
    elif choice == "2":
        send_message()
    elif choice == "3":
        view_messages()
    elif choice == "4":
        print("Goodbye!")
        break
    else:
        print("Invalid choice! Please try again.")