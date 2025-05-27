# Cryptocurrency
crypto_db = {
    "Bitcoin": {
        "price_trend": "rising",
        "market_cap": "high",
        "energy_use": "high",
        "sustainability_score": 3 / 10,
    },
    "Ethereum": {
        "price_trend": "stable",
        "market_cap": "high",
        "energy_use": "medium",
        "sustainability_score": 6 / 10,
    },
    "Cardano": {
        "price_trend": "rising",
        "market_cap": "medium",
        "energy_use": "low",
        "sustainability_score": 8 / 10,
    },
}
  FULL WORKING PYTHON CODE
  crypto_db = {
    "Bitcoin": {
        "price_trend": "rising",
        "market_cap": "high",
        "energy_use": "high",
        "sustainability_score": 3 / 10,
    },
    "Ethereum": {
        "price_trend": "stable",
        "market_cap": "high",
        "energy_use": "medium",
        "sustainability_score": 6 / 10,
    },
    "Cardano": {
        "price_trend": "rising",
        "market_cap": "medium",
        "energy_use": "low",
        "sustainability_score": 8 / 10,
    },
}

def get_most_sustainable():
    recommend = max(crypto_db, key=lambda x: crypto_db[x]["sustainability_score"])
    score = crypto_db[recommend]["sustainability_score"]
    return f"Invest in {recommend}! 🌱 It’s eco-friendly with a sustainability score of {score*10:.1f}/10."

def get_trending_up():
    trending_coins = [
        coin for coin, data in crypto_db.items()
        if data["price_trend"] == "rising" and data["market_cap"] == "high"
    ]
    if trending_coins:
        return f"{', '.join(trending_coins)} are trending up with high market caps! 🚀"
    else:
        return "No top coins are trending up right now with high market caps. Try asking again later!"

def get_long_term_growth():
    # Balance rising price trend and sustainability score >= 7/10
    candidates = [
        coin for coin, data in crypto_db.items()
        if data["price_trend"] == "rising" and data["sustainability_score"] >= 0.7
    ]
    if candidates:
        details = ", ".join([f"{coin} ({crypto_db[coin]['sustainability_score']*10:.1f}/10 sustainability)" for coin in candidates])
        return f"For long-term growth, consider {details}! 🚀🌿"
    else:
        return "No coins match both rising trend and high sustainability right now. Research carefully!"

def crypto_buddy_bot():
    print("CryptoBuddy 🤖: Hey there! Ask me about crypto trends or sustainability. Type 'exit' to quit.")
    while True:
        user_query = input("You: ").lower()

        if user_query == "exit":
            print("CryptoBuddy 🤖: Bye! Remember, crypto is risky—always do your own research! 📚")
            break

        if "sustainable" in user_query or "eco" in user_query:
            response = get_most_sustainable()
        elif "trending up" in user_query or "rising" in user_query:
            response = get_trending_up()
        elif "long-term growth" in user_query or "long term" in user_query:
            response = get_long_term_growth()
        else:
            response = "Sorry, I didn't get that. Try asking about 'sustainable coins', 'trending up', or 'long-term growth'."

        print(f"CryptoBuddy 🤖: {response}")

# Run the chatbot
crypto_buddy_bot()

  
