# quote-based-on-your-name
import random

# Define a dictionary of categories and corresponding quotes
quote_collections = {
    "motivation": [
        "Success is not final, failure is not fatal: It is the courage to continue that counts. - {name}",
        "Believe you can and you're halfway there. - {name}",
        "Don't watch the clock; do what it does. Keep going. - {name}",
        "Let what comes come, let what goes go. - {name}",
    ],
    "success": [
        "Success is not the key to happiness. Happiness is the key to success. If you love what you are doing, you will be successful. - {name}",
        "Success is walking from failure to failure with no loss of enthusiasm. - {name}",
        "The only place where success comes before work is in the dictionary. - {name}",
        "Let what comes come, let what goes go. - {name}",
    ],
    "life": [
        "Life is 10% what happens to us and 90% how we react to it. - {name}",
        "In three words I can sum up everything I've learned about life: it goes on. - {name}",
        "Life is really simple, but we insist on making it complicated. - {name}",
        "Let what comes come, let what goes go. - {name}",
    ],
    "love": [
        "The best thing to hold onto in life is each other. - {name}",
        "To love and be loved is to feel the sun from both sides. - {name}",
        "Love is not finding someone to live with, it's finding someone you can't live without. - {name}",
        "Tears are words the heart can't express. -{name}",
    ],
    "friendship": [
        "A real friend is one who walks in when the rest of the world walks out.- {name}",
        "A friend is one of the best things you can be and the greatest things you can have. - {name}",
        "Time doesn't take away from friendship, nor does separation. - {name}",
        "it is a good and gentle religion, but inconvenient.  -{name}",
    ],
    "devotional": [
        "You are what you believe in. You become that which you believe you can become. - {name}",
        "Every day you should sit quietly and affirm, with deep conviction. - {name}",
        "We behold what we are, and we are what we behold. - {name}",
        "Ahimsa Paramodharmah -{name}",
    ],
}


def generate_personalized_quote():
    name = input("Enter your name: ")
    print("Select a category for the quote:")
    for index, category in enumerate(quote_collections.keys(), start=1):
        print(f"{index}. {category.capitalize()}")

    category_choice = None
    while category_choice not in quote_collections:
        try:
            choice_num = int(input("Enter the number of the chosen category: "))
            category_choice = list(quote_collections.keys())[choice_num - 1]
        except (ValueError, IndexError):
            print("Invalid input. Please enter a valid number.")

    random_quote = random.choice(quote_collections[category_choice])
    personalized_quote = random_quote.format(name=name)
    print("\nHere's your personalized quote:")
    print(personalized_quote)


generate_personalized_quote()
