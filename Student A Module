import random

# ✅ 200-word bank
WORD_BANK = [
    "APPLE","BRUSH","CHARM","DREAM","ELDER","FLAME","GRAPE","HOUSE","INDEX","JAUNT",
    "KNEEL","LEMON","MAPLE","NOVEL","OCEAN","PAINT","QUIRK","RIVER","SLATE","TIGER",
    "URBAN","VALUE","WATER","XENON","YEAST","ZEBRA","ADAPT","BACON","CANOE","DRIFT",
    "EXACT","FIELD","GUARD","HOTEL","IVORY","JOLLY","KAYAK","LATCH","MANGO","NICHE",
    "ORBIT","PLANT","QUOTA","RELAY","SOUND","THORN","ULCER","VOCAL","WAGER","XEROX",
    "YODEL","ZIGGY","ARISE","BISON","CEDAR","DANCE","EAGLE","FRESH","GRAIN","IMPLY",
    "JUDGE","KHAKI","LOGIC","MURAL","MUSIC","OFFER","PRISM","QUEEN","ROUTE","SHOCK",
    "TRACE","UNITE","VISTA","XYLEM","YOUTH","ABOUT","BOUND","CRISP","DEPTH","ENTRY",
    "FOCUS","GRASP","HURRY","ISSUE","JEWEL","LAYER","NORTH","OLIVE","PROBE","ROYAL",
    "SHADY","TIGHT","VIVID","WITCH","XENIC","YIELD","ZONED","ALTAR","BRAID","CLASP",
    "DIARY","EQUAL","FABLE","IDEAL","KNEAD","LUNAR","MERCY","NODAL","OZONE","PEACH",
    "QUERY","RALLY","SOLAR","TWIST","USHER","VAULT","WAGON","YACHT","ANGEL","BENCH",
    "COURT","DRUNK","FLEET","GLASS","INNER","KOALA","LUNGE","MODAL","NEEDY","ONSET",
    "PORCH","QUAIL","REALM","TORCH","UNION","VEGAS","WEARY","XENIA","YEARN","AMAZE",
    "BRISK","CLOVE","DOZEN","ERASE","FRANK","GRIPE","HASTE","LARGE","NOBLE","PRIME",
    "QUASH","RIDGE","TALON","VERGE","WHARF","ZONAL","ARIAL","CARGO","DASHY","EXCEL",
    "FUZZY","HUMUS","INLET","KVELL","NIFTY","OPINE","PIXEL","QUERN","ROUSE","SERGE",
    "THYME","VIPER","WAVER","XYLAR","YELPS","ZAPPY",
    "BLEND","CRANE","SLICE","BRAVE","CHANT","PLUMB","GLIDE",
    "TRAIL","SWEET","DRIVE","CLOUD","STONE","SHARE","LIGHT"
]

# 🎚️ Difficulty lists (simple split)
EASY_WORDS = [word for word in WORD_BANK if word not in [
    "XENON","XYLEM","XEROX","KVELL","QUERN","XYLAR","ZAPPY","XENIC","XENIA"
]]

HARD_WORDS = [word for word in WORD_BANK if word not in EASY_WORDS]


# 🔤 Normalize input
def normalize_input(word):
    return word.strip().upper()


# 📏 Check word length
def is_valid_length(word):
    return len(word) == 5


# 📚 Check if word exists
def is_real_word(word, word_list):
    return word in word_list


# ✅ Full validation
def validate_guess(input_word, word_list):
    word = normalize_input(input_word)

    if not is_valid_length(word):
        return False, "Word must be exactly 5 letters."

    if not word.isalpha():
        return False, "Word must contain only letters."

    if not is_real_word(word, word_list):
        return False, "Word not in word list."

    return True, word


# 🎲 Select word by difficulty
def select_word(difficulty="easy"):
    if difficulty == "easy":
        return random.choice(EASY_WORDS)
    elif difficulty == "hard":
        return random.choice(HARD_WORDS)
    else:
        return random.choice(WORD_BANK)


# 🧪 Example test run
if __name__ == "__main__":
    mode = input("Choose difficulty (easy/hard): ").lower()
    target_word = select_word(mode)

    print("DEBUG (remove later):", target_word)  # remove in final game

    guess = input("Enter your guess: ")
    valid, result = validate_guess(guess, WORD_BANK)

    if valid:
        print("Valid guess:", result)
    else:
        print("Error:", result)
