# Week 4 Assignment: The Expense Categorizer

print("===== Expense Categorizer =====")

# Get user input
amount = input("Enter expense amount: ")
description = input("Enter expense description: ")

# Validate description
if description.strip() == "":
    print("Error: Description cannot be empty.")

# Validate amount
elif not amount.isdigit():
    print("Error: Amount must be a whole number.")

elif int(amount) <= 0:
    print("Error: Amount must be greater than 0.")

else:
    # Convert amount to integer
    amount = int(amount)

    # Convert description to lowercase for easy matching
    desc = description.lower()

    # Categorize expense
    if "bus" in desc or "taxi" in desc or "fuel" in desc:
        category = "Transport"

    elif "lunch" in desc or "market" in desc or "groceries" in desc:
        category = "Food"

    elif "rent" in desc or "electricity" in desc or "water" in desc:
        category = "Utilities"

    else:
        category = "Other"

    # Display results
    print("\n===== Expense Summary =====")
    print("Amount: ", amount)
    print("Description:", description)
    print("Category:", category)

    # Flag expensive transactions
    if amount > 5000:
        print("Status: Expense flagged for review.")
    else:
        print("Status: Expense recorded successfully.")
