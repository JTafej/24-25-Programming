### **Hello Everyone!**

I'm sorry I can't be there today—I’m writing letters of recommendation. However, I have a lesson for you to work through, please follow along with what's below!

#### **First: Complete Your To-Do List Project**
If you didn’t finish the to-do list project from yesterday, **start by completing it now**. Make sure you have added all the features, like viewing tasks, adding tasks, removing tasks, and quitting the app.

#### **Before you start today's lesson: Ensure All Previous Assignments Are Complete**
Before starting today’s lesson, make sure you have completed all your prior assignments, including the projects on conditionals, loops, and lists. If you're all caught up, you're ready to move on to today’s lesson!

---

### **Today's Lesson: Combining Lists, Loops, Conditionals, and Random**

Today, we're going to use some of the skills you've learned so far to create a small program that generates a **random adventure scenario**. You’ll use lists, loops, conditionals, and some creativity to complete the tasks. Follow along with each step below, and comment out your code as you work on each task so I can see your thought process!

---

#### **Step 3: Creating a Simple Scenario Generator**

You’ll create a simple adventure story generator that pulls random items from lists and puts them together into a short narrative.

1. **Create three lists**:
   - One list for **characters** (like “a knight,” “a wizard,” “a thief,” etc.).
   - One list for **settings** (like “in a dark forest,” “in a mystical cave,” “in a busy village,” etc.).
   - One list for **actions** (like “fights a dragon,” “finds a treasure,” “gets lost,” etc.).

Here’s a starting example of how to create and print one item from each list:

```
python
import random

# List of characters
characters = ["a knight", "a wizard", "a thief"]

# List of settings
settings = ["in a dark forest", "in a mystical cave", "in a busy village"]

# List of actions
actions = ["fights a dragon", "finds a treasure", "gets lost"]

# Randomly select one of each
character = random.choice(characters)
setting = random.choice(settings)
action = random.choice(actions)

# Print the scenario
print(f"{character} {setting} and {action}.")
```

#### **Task 1:** Add **at least 5** options to each list (characters, settings, and actions).  
*Comment this out when you’re done.*

---

#### **Step 4: Using Loops for Multiple Scenarios**

Now, let's generate multiple scenarios instead of just one. We’ll use a loop for this.

2. **Create a loop** that generates **5 random scenarios**. You can do this using a `for` loop.

Here’s an example to get you started:

```python
for i in range(5):
    character = random.choice(characters)
    setting = random.choice(settings)
    action = random.choice(actions)
    print(f"{character} {setting} and {action}.")
```

#### **Task 2:** Make sure your loop prints **five different scenarios**.  
*Comment this out when you’re done.*

---

#### **Step 5: Adding User Input**

Let's make this a bit more interactive by asking the user how many scenarios they want to generate.

3. **Ask the user** how many scenarios they want to generate, then use a loop to generate that many. You can use the `input()` function for this.

Example:

```python
num_scenarios = int(input("How many scenarios would you like to generate? "))

for i in range(num_scenarios):
    character = random.choice(characters)
    setting = random.choice(settings)
    action = random.choice(actions)
    print(f"{character} {setting} and {action}.")
```

#### **Task 3:** Ask the user how many scenarios they want to generate and make sure your loop generates that number.  
*Comment this out when you’re done.*

---

#### **Step 6: Adding Conditionals**

Let’s add some variety to our story generator by using conditionals. For example, if a character is "a wizard," they might always "cast a spell" instead of getting random actions.

4. **Modify your program** to use `if` statements. If the character is "a wizard," always have them “cast a spell” instead of using a random action. Otherwise, they should perform a random action.

Example:

```python
for i in range(num_scenarios):
    character = random.choice(characters)
    setting = random.choice(settings)
    
    if character == "a wizard":
        action = "casts a spell"
    else:
        action = random.choice(actions)
    
    print(f"{character} {setting} and {action}.")
```

#### **Task 4:** Add a condition for one of your characters so that they always perform a specific action.  
*Comment this out when you’re done.*

---

### **Challenge: Creating a More Complex Scenario Generator**

Here’s the challenge for today. Expand on the program you've built by adding **more complexity**. Here are some ideas for how you could do this:
- Add **different outcomes** depending on the action (use conditionals to decide if they succeed or fail at their action).
- Add a **points system** where each scenario gives or takes away points based on the outcome.
- Include a **list of items** the character might find or use during the adventure.

**Your Challenge for the day** Modify your scenario generator to be more complex in *any way* you choose. Be creative, and think of how you can apply lists, loops, conditionals, and user input to make it more interesting!

---

### **Final Notes**
Please make sure you’ve commented out all the small tasks after you complete them. If you finish everything early, feel free to review any past lessons or add more features to your to-do list app or this adventure generator. Or look up something new!

Let me know if you have any questions when I’m back. Have fun!
