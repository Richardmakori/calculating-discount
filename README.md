# calculating-discount
# Define the function to calculate the discount
def calculate_discount(price, discount_percent):
    # Check if the discount is 20% or higher
    if discount_percent >= 20:
        # Apply the discount
        discount_amount = price * (discount_percent / 100)
        final_price = price - discount_amount
        return final_price
    else:
        # Return the original price if the discount is less than 20%
        return price

# Function to get valid user input
def get_float_input(prompt):
    while True:
        try:
            value = float(input(prompt))
            if value < 0:
                print("Please enter a positive number.")
                continue
            return value
        except ValueError:
            print("Invalid input. Please enter a valid number.")

# Main program
print("Welcome to the Discount Calculator!")

# Get the original price and discount percentage from the user
price = get_float_input("Enter the original price of the item: $")
discount_percent = get_float_input("Enter the discount percentage: ")

# Calculate the final price
final_price = calculate_discount(price, discount_percent)

# Print the result
if final_price == price:
    print(f"No discount applied. The price remains: ${final_price:.2f}")
else:
    print(f"The final price after applying the discount is: ${final_price:.2f}")
