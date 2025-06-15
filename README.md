# Temperature-Converter

def celsius_to_fahrenheit(celsius):
    return (celsius * 9/5) + 32

def fahrenheit_to_celsius(fahrenheit):
    return (fahrenheit - 32) * 5/9

def celsius_to_kelvin(celsius):
    return celsius + 273.15

def kelvin_to_celsius(kelvin):
    return kelvin - 273.15

def fahrenheit_to_kelvin(fahrenheit):
    return celsius_to_kelvin(fahrenheit_to_celsius(fahrenheit))

def kelvin_to_fahrenheit(kelvin):
    return celsius_to_fahrenheit(kelvin_to_celsius(kelvin))

print("Select conversion type:")
print("1. Celsius to Fahrenheit")
print("2. Fahrenheit to Celsius")
print("3. Celsius to Kelvin")
print("4. Kelvin to Celsius")
print("5. Fahrenheit to Kelvin")
print("6. Kelvin to Fahrenheit")

while True:
    choice = input("Enter choice(1/2/3/4/5/6): ")

    if choice in ('1', '2', '3', '4', '5', '6'):
        try:
            value = float(input("Enter temperature value: "))
        except ValueError:
            print("Invalid input. Please enter a number.")
            continue

        if choice == '1':
            print(f"{value}°C is {celsius_to_fahrenheit(value):.2f}°F")
        elif choice == '2':
            print(f"{value}°F is {fahrenheit_to_celsius(value):.2f}°C")
        elif choice == '3':
            print(f"{value}°C is {celsius_to_kelvin(value):.2f}K")
        elif choice == '4':
            print(f"{value}K is {kelvin_to_celsius(value):.2f}°C")
        elif choice == '5':
            print(f"{value}°F is {fahrenheit_to_kelvin(value):.2f}K")
        elif choice == '6':
            print(f"{value}K is {kelvin_to_fahrenheit(value):.2f}°F")
        
        next_conversion = input("Do you want to perform another conversion? (yes/no): ")
        if next_conversion.lower() != 'yes':
            break
    else:
        print("Invalid Input. Please enter a valid choice (1-6).")

