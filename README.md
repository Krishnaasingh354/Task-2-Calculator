# Task-2-Calculator
def add(x, y):
    """Addition"""
    return x + y

def subtract(x, y):
    """Subtraction"""
    return x - y

def multiply(x, y):
    """Multiplication"""
    return x * y

def divide(x, y):
    """Division"""
    if y == 0:
        return "Error! Division by zero."
    return x / y

def display_menu():
    """Display calculator menu"""
    print("\n" + "="*50)
    print("CALCULATOR".center(50))
    print("="*50)
    print("Select operation:")
    print("1. Addition (+)")
    print("2. Subtraction (-)")
    print("3. Multiplication (*)")
    print("4. Division (/)")
    print("5. Exit")
    print("="*50)

def get_number(prompt):
    """Get number input from user"""
    while True:
        try:
            return float(input(prompt))
        except ValueError:
            print("Invalid input! Please enter a valid number.")

def main():
    print("\n🔢 Welcome to Python Calculator!")
    
    while True:
        display_menu()
        choice = input("\nEnter choice (1-5): ").strip()
        
        if choice == '5':
            print("\n👋 Thank you for using the calculator. Goodbye!")
            break
        
        if choice in ['1', '2', '3', '4']:
            num1 = get_number("Enter first number: ")
            num2 = get_number("Enter second number: ")
            
            if choice == '1':
                result = add(num1, num2)
                print(f"\n✓ Result: {num1} + {num2} = {result}")
            
            elif choice == '2':
                result = subtract(num1, num2)
                print(f"\n✓ Result: {num1} - {num2} = {result}")
            
            elif choice == '3':
                result = multiply(num1, num2)
                print(f"\n✓ Result: {num1} × {num2} = {result}")
            
            elif choice == '4':
                result = divide(num1, num2)
                print(f"\n✓ Result: {num1} ÷ {num2} = {result}")
        
        else:
            print("\n✗ Invalid choice! Please select 1-5.")
        
        # Ask if user wants to continue
        continue_calc = input("\nPerform another calculation? (yes/no): ").lower()
        if continue_calc not in ['yes', 'y']:
            print("\n👋 Thank you for using the calculator. Goodbye!")
            break

if __name__ == "__main__":
    main()
