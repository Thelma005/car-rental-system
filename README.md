
# Simple Inventory System

# Dictionary to store inventory items and their quantities
inventory = {}

def add_item(name, quantity):
    """Adds an item to the inventory or updates its quantity if it exists."""
    if name in inventory:
        inventory[name] += quantity
        print(f"Updated {name} quantity to {inventory[name]}.")
    else:
        inventory[name] = quantity
        print(f"Added {name} to the inventory with quantity {quantity}.")

def get_item(name):
    """Retrieves information about a specific item in the inventory."""
    if name in inventory:
        print(f"{name}: {inventory[name]}")
    else:
        print(f"{name} is not in the inventory.")

def calculate_total_quantity():
    """Calculates and displays the total quantity of all items in the inventory."""
    total = sum(inventory.values())
    print(f"Total quantity of all items: {total}")

# Main program loop
while True:
    print("\nInventory Menu:")
    print("1. Add/Update Item")
    print("2. Retrieve Item Info")
    print("3. Display Total Quantity")
    print("4. Exit")
    choice = input("Enter your choice: ")
    
    if choice == "1":
        item_name = input("Enter the item name: ")
        try:
            item_quantity = int(input("Enter the quantity: "))
            add_item(item_name, item_quantity)
        except ValueError:
            print("Invalid quantity. Please enter a number.")
    elif choice == "2":
        item_name = input("Enter the item name to retrieve: ")
        get_item(item_name)
    elif choice == "3":
        calculate_total_quantity()
    elif choice == "4":
        print("Exiting the program.")
        break
    else:
        print("Invalid choice. Please try again.")