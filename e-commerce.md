products = {
    1: {"name": "Laptop", "price": 50000},
    2: {"name": "Smartphone", "price": 20000},
    3: {"name": "Headphones", "price": 1500},
    4: {"name": "Keyboard", "price": 700}
}
cart = []
# Display product list
def show_products():
    print("\nAvailable Products:")
    for pid, info in products.items():
        print(f"{pid}. {info['name']} - ₹{info['price']}")

# Add product to cart
def add_to_cart():
    pid = int(input("Enter Product ID to add to cart: "))
    if pid in products:
        cart.append(products[pid])
        print(f"{products[pid]['name']} added to cart.")
    else:
        print("Invalid Product ID.")
# View cart items
def view_cart():
    if not cart:
        print("Your cart is empty.")
        return
    print("\nItems in Cart:")
    total = 0
    for item in cart:
        print(f"- {item['name']} - ₹{item['price']}")
        total += item['price']
    print(f"Total: ₹{total}")
# Checkout
def checkout():
    if not cart:
        print("Your cart is empty.")
        return
    view_cart()
    print("Proceeding to payment...")
    print("Payment successful! Thank you for shopping.")
    cart.clear()
# Main menu loop
while True:
    print("\n==== E-Commerce Menu ====")
    print("1. Show Products")
    print("2. Add to Cart")
    print("3. View Cart")
    print("4. Checkout")
    print("5. Exit")
    choice = input("Enter your choice: ")
    if choice == '1':
        show_products()
    elif choice == '2':
        show_products()
        add_to_cart()
    elif choice == '3':
        view_cart()
    elif choice == '4':
        checkout()
    elif choice == '5':
        print("Exiting... Goodbye!")
        break
    else:
        print("Invalid choice. Try again.")
