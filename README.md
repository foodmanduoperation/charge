#Deliverycharge
# Define delivery charge constants
BASE_DELIVERY_CHARGE = 50.00

# Define function to calculate delivery charge based on distance and order value
def calculate_delivery_charge(distance_in_km, order_value):
    if order_value < 1000:
        delivery_charge = BASE_DELIVERY_CHARGE + (15.00 * distance_in_km)
        if distance_in_km > 6:
            delivery_charge += (distance_in_km - 6) * 5.00
    elif order_value < 1500:
        delivery_charge = BASE_DELIVERY_CHARGE + (10.00 * distance_in_km)
        if distance_in_km > 2:
            delivery_charge += (distance_in_km - 2) * 15.00
        if distance_in_km > 6:
            delivery_charge += (distance_in_km - 6) * 5.00
    else:
        delivery_charge = 50.00
        if distance_in_km > 2:
            delivery_charge += (distance_in_km - 2) * 20.00
        if distance_in_km > 6:
            delivery_charge += (distance_in_km - 6) * 5.00
    return delivery_charge

# Example usage
distance = 4.5 # Distance in km from restaurant to customer
order_value = 1200 # Order value in rupees
delivery_charge = calculate_delivery_charge(distance, order_value)
print(f"Delivery charge: Rs. {delivery_charge:.2f}")
