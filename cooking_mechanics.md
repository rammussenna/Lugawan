#  Ingredient System Design (Section 2 of Cooking Mechanics)

##  Goal:

core set of ingredients that supports:

* Simple recipes early on
* Progressive complexity (more toppings, customer preferences)
* Story-triggered corruption or "wrongness" in later gameplay

---

##  Ingredient Types

### 1. **Core Essentials** *(used in almost every recipe)*

| Ingredient          | Use                          | Notes                               |
| ------------------- | ---------------------------- | ----------------------------------- |
| **Bigas (Rice)**    | Base for lugaw/goto          | Must be boiled                      |
| **Tubig (Water)**   | Combined with rice           | Can be clean or dirty (twist event) |
| **Luya (Ginger)**   | Always part of base flavor   | May rot in later                    |
| **Fried Garlic Bits**   | Common topping                               | Must be perfectly cooked           |
| **Sibuyas (Onion)** | Optional flavor or request   | Skipping can upset some customers   |

---

### 2. **Main Protein Add-ons**

| Ingredient          | Use                  | Notes                                   |
| ------------------- | -------------------- | --------------------------------------- |
| **Tokwa (Tofu)**    | For *Tokwa’t Baboy*  | Must be deep-fried or pan-fried         |
| **Baboy (Pork)**    | For *Goto* or combo  | Needs pre-boil or sauté                 |
| **Itlog na Maalat** | Optional topping     | Slice before serving                    |
| **Chicken**         | Arroz caldo-specific | Appears later in game or special events |

---

### 3. **Garnishes, Side Items, and Custom Requests**

| Ingredient                     | Use                                          | Notes                              |
| ------------------------------ | -------------------------------------------- | ---------------------------------- |
| **Calamansi**                  | Optional acidity                             | Players can forget it              |
| **Sili / Chili Oil**           | For “spicy” requests                         | May trigger dialogue               |
| **Black Pepper**               | Secret option, not always shown              | Story-relevant one day             |
| **Chicharon**                  | Rare topping / unlockable                    | High-tier order item               |
| **Lumpia**                     | Not for lugaw but side order (money booster) | Adds variation in late-game rushes |

---

##  Late-Game / Narrative Trigger Ingredients (Spoiler Mechanics)

| Ingredient                          | Use                                       | Notes                               |
| ----------------------------------- | ----------------------------------------- | ----------------------------------- |
| **“Panis na Bigas” (Spoiled Rice)** | Replaces rice in some loops               | Can’t tell unless observed closely  |
| **“Itlog na Itim” (Rotten Egg)**    | Visually normal, wrong after boiling      | Symbolic of decay                   |
| **“Hindi Ko Alam” (??? Meat)**      | Unidentifiable protein appears in fridge  | Game does not label it              |
| **Dugo?” (Bloody broth)**           | Shows when overcooked or on specific days | May trigger hallucination sequence  |
| **Inverted Calamansi**              | Appears inside-out, skin on the inside    | Early signal of “something's wrong” |

---

##  Ingredient Properties (Technical)

For engine use or system planning:

| Property          | Description                           | Example                               |
| ----------------- | ------------------------------------- | ------------------------------------- |
| **Perishability** | Some ingredients expire               | Luya, Baboy                           |
| **Prep Type**     | Raw, Boiled, Fried, Sliced            | Tokwa = fried                         |
| **Mood Modifier** | Impacts customer dialogue/mood        | Garlic adds +1 satisfaction           |
| **Hidden Flag**   | For story tracking                    | Using wrong broth = mark “Glitch Day” |
| **Visual Decay**  | Sprite/art changes based on freshness | Gray meat, wilted calamansi           |

---

##  Pantry & Inventory System

| Mechanic             | Description                                        |
| -------------------- | -------------------------------------------------- |
| **Stock Limit**      | You have a certain amount of each item per day     |
| **Restock Decision** | Between days, use income to buy more supplies      |
| **Spoilage**         | Fridge/pantry contents rot over time if not used   |
| **Miscalculation**   | Forgetting to buy onions = customer reaction chain |
| **Dynamic Supply**   | Some days, pork is unavailable (e.g., “meat ban”)  |
