# control-flow
def calculate_discount(price, discount_percent):
    Calculate the final price after applying a discount.
    Parameters:
    price (float): The original price of the item.
    discount_percent (float): The discount percentage to apply.

  Returns:
    float: The final price after applying the discount, or the original price if the discount is less than 20%.
    """
    if discount_percent >= 20:
        discount_amount = (discount_percent / 100) * price
        final_price = price - discount_amount
        return final_price
    else:
        return price

# Prompt the user for input
try:
    original_price = float(input("Enter the original price of the item: "))
    discount_percentage = float(input("Enter the discount percentage: "))
    # Validate that the inputs are non-negative
    if original_price < 0 or discount_percentage < 0:
        print("Please enter non-negative values for price and discount percentage.")
    else:
        # Calculate the final price
        final_price = calculate_discount(original_price, discount_percentage)
   # Display the result
   if discount_percentage >= 20:
            print(f"After applying a {discount_percentage}% discount, the final price is: ${final_price:.2f}")
        else:
            print(f"No discount applied. The price remains: ${final_price:.2f}")
except ValueError:
    print("Invalid input. Please enter numeric values for price and discount percentage.")
