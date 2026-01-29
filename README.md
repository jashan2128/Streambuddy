# Streambuddy

StreamBuddy is a Python command-line app that helps YouTube streamers come up with cool stream titles, fun descriptions, trendy hashtags, and catchy thumbnail text—all based on whatever you type in.



streambuddy

│

├── main.py

├── README.md

├── generator

│   ├── \_\_init\_\_.py

│   ├── title.py

│   ├── description.py

│   ├── hashtags.py

│   └── thumbnail.py

└── data



import random



def generate\_title(game, style, friends):

    templates = \[

        f"{style} {game} Stream 🔥",

        f"Playing {game} | {style} vibes 🎮",

        f"{game} with {'Friends' if friends else 'Solo'} 😎",

        f"Late Night {game} Stream 🌙",

        f"{style} {game} Chaos 😂"

    ]

    return random.choice(templates)



def generate\_description(game, style, friends):

    short = f"Join me for a {style.lower()} {game} live stream!"

 

    long = (

        f"Welcome to the stream! 🎮\\n\\n"

        f"Today we are playing {game} in a {style.lower()} style. "

        f"{'Playing with friends for extra fun!' if friends else 'Solo grind today!'}\\n\\n"

        f"Drop a like, subscribe, and enjoy the stream ❤️"

    )

    return short, long



def generate\_hashtags(game):

    base = game.lower().replace(" ", "")

    hashtags = \[

        f"#{base}",

        "#gaming",

        "#gaminglive",

        "#youtubelive",

        "#indiangamer"

    ]

    return " ".join(hashtags)



import random



def generate\_thumbnail\_text(game):

    texts = \[

        f"{game.upper()} LIVE",

        "THIS GOT CRAZY 😳",

        "INSANE MATCH 🔥",

        "FUN WITH FRIENDS 😂",

        "DON'T MISS THIS!"

    ]

    return random.choice(texts)

from generator.title import generate\_title

from generator.description import generate\_description

from generator.hashtags import generate\_hashtags

from generator.thumbnail import generate\_thumbnail\_text



print("🎮 Welcome to StreamBuddy 🎮\\n")



game = input("Enter game name: ")

style = input("Stream style (Chill/Funny/Competitive): ")

friends\_input = input("Playing with friends? (y/n): ")



friends = friends\_input.lower() == "y"



print("\\n✨ Generating Stream Content...\\n")



title = generate\_title(game, style, friends)

short\_desc, long\_desc = generate\_description(game, style, friends)

hashtags = generate\_hashtags(game)

thumbnail = generate\_thumbnail\_text(game)



print("📌 TITLE:")

print(title)



print("\\n📝 SHORT DESCRIPTION:")

print(short\_desc)



print("\\n📄 FULL DESCRIPTION:")

print(long\_desc)



print("\\n#️⃣ HASHTAGS:")

print(hashtags)



print("\\n🖼️ THUMBNAIL TEXT:")

print(thumbnail)



print("\\n✅ Done! Happy Streaming 🚀")

