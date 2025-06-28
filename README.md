import openai

# Set your OpenAI API key
openai.api_key = "your-api-key-here"

def chat_with_gpt(prompt):
    try:
        # Call the OpenAI API
        response = openai.ChatCompletion.create(
            model="gpt-4",  # Use "gpt-3.5-turbo" or "gpt-4" based on your subscription
            messages=[
                {"role": "system", "content": "You are a helpful assistant."},
                {"role": "user", "content": prompt}
            ],
            max_tokens=150,
            temperature=0.7
        )
        # Extract and return the assistant's reply
        return response['choices'][0]['message']['content'].strip()
    except Exception as e:
        return f"An error occurred: {e}"

# Example usage
if __name__ == "__main__":
    print("GdAi: Hello! How can I assist you in Geometry dash?")
    while True:
        user_input = input("You: ")
        if user_input.lower() in ["exit", "quit", "bye"]:
            print("GdAi: Goodbye! Have a great day!")
            break
        reply = chat_with_gpt(user_input)
        print(f"GdAi: {reply}")


        import tkinter as tk
from tkinter import font

def change_font(event=None):
    selected_font = font_var.get()
    text_label.config(font=(selected_font, 16))

# Create the main window
root = tk.Tk()
root.title("Font Changer")

# Available fonts
available_fonts = list(font.families())

# Dropdown menu for font selection
font_var = tk.StringVar(value="

Oxygene 1")
font_menu = tk.OptionMenu(root, font_var, *available_fonts, command=change_font)
font_menu.pack(pady=10)

# Label to display text with the selected font
text_label = tk.Label(root, text="Hello, change my font!", font=("Arial", 16))
text_label.pack(pady=20)

# Run the application
root.mainloop()


