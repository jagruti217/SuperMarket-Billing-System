# SuperMarket-Billing-System
A Python-based supermarket billing system that allows customers to add items to a cart, view a menu with prices, and generate a detailed receipt. It calculates subtotals, applies discounts, and displays the final amount. The code is modular, demonstrating basic Python concepts like loops, functions, and input validation

## How to Run the Program

1. **Requirements:** Make sure you have Python installed on your system (Python 3.6 or higher is recommended).
2. **Run the Code:** Execute the code in a Python environment (e.g., Jupyter Notebook, VS Code, or directly from the command line).
3. **Follow the Prompts:** The program will prompt you to enter your name, phone number, and then add items to your cart. After adding items, you can print the receipt to see the final bill.


```
python
products = {
    "Chips": 20,
    "Cola": 40,
    "Apples": 100,
    "Bananas": 30,
    "Notebook": 50,
    "Milk": 60,
    "Bread": 25,
    "Eggs": 80,
    "Cheese": 120,
    "Butter": 70,
    "Chocolate": 45,
    "Orange Juice": 70,
    "Tomatoes": 35,
    "Cucumbers": 25,
    "Potatoes": 40,
    "Carrots": 30,
    "Shampoo": 150,
    "Soap": 35,
    "Toothpaste": 75,
    "Rice": 200,
    "Pasta": 60,
    "Coffee": 110,
    "Tea": 70,
    "Sugar": 50,
    "Salt": 20,
    "Cooking Oil": 140,
    "Flour": 60,
    "Biscuits": 30,
    "Yogurt": 45,
    "Ice Cream": 90
}

while True:
    cart = {}
    amount = 0
    name = input("enter name: ").title()
    ph_no = input("enter phone number: ")
    print("-"*60)
    print("enter quantity and price")
    
    while True:
        quantity = float(input("enter quantity: "))
        while True:
            p_name = input("enter item name: ").title()
            if p_name not in products.keys():
                print("try again with the correct spelling")
            else:
                break
        amount += products[p_name] * quantity
        cart[p_name] = products[p_name],"x",quantity
        repeat_item = input("do you want to add more items?(yes/no) ").lower()
        if repeat_item in ["no","n"]:
            break
    discount = 0
    
    if amount <= 500:
        discount = 0.05
        act_amount = amount - (amount* discount)
    elif amount <= 1000:
        discount = 0.07
        act_amount = amount - (amount* discount)
    elif amount<= 5000:
        distinct = 0.15
        act_amount = amount - (amount* discount)
    else:
        discount = 0.2
        act_amount = (amount - discount)
        
    print("-"*60)

    print("SUPER MARKET STORE".center(50))
    print("Carter Road, Andheri West, Phone: 321-356-401".center(50))
    print("-"*60)
    print("-"*60)
    
    print("Customer Name     :   ", name)
    print("Customer Phone    :   ", ph_no)
    print("-"*60)
    for i,j in cart.items():
        p,x,q = j
        print(i, ":",p,x,q)

    print("-"*60)
            
    print("Total bill        :  ", "₹",amount)
    print("Discount Applied  :  ", discount*100, "%OFF")
    print("Actual Amount     :  ", "₹",act_amount)
    print("")
    print("-"*60)
    
    print ("\n")
    print("Thankyou For Shopping with us ^_^".center(50))
    print("\n")
    print("-"*60)
    print("-"*60)
    print("\n")
    next_person = input("is there a next person in the queue? (yes/no): ").lower()
    if next_person in ["no","n"]:
        break


## Example Output

```enter name:  Ayushi
enter phone number:  9892363538
------------------------------------------------------------
enter quantity and price
enter quantity:  5
enter item name:  Rice
do you want to add more items?(yes/no)  Yes
enter quantity:  4
enter item name:  Tea
do you want to add more items?(yes/no)  Yes
enter quantity:  3
enter item name:  Coffee
do you want to add more items?(yes/no)  Yes
enter quantity:  7
enter item name:  Pasta
do you want to add more items?(yes/no)  Yes
enter quantity:  2
enter item name:  Shampoo
do you want to add more items?(yes/no)  no
------------------------------------------------------------
                SUPER MARKET STORE                
  Carter Road, Andheri West, Phone: 321-356-401   
------------------------------------------------------------
------------------------------------------------------------
Customer Name     :    Ayushi
Customer Phone    :    9892363538
------------------------------------------------------------
Rice : 200 x 5.0
Tea : 70 x 4.0
Coffee : 110 x 3.0
Pasta : 60 x 7.0
Shampoo : 150 x 2.0
------------------------------------------------------------
Total bill        :   ₹ 2330.0
Discount Applied  :   0 %OFF
Actual Amount     :   ₹ 2330.0

------------------------------------------------------------


        Thankyou For Shopping with us ^_^         


------------------------------------------------------------
------------------------------------------------------------
```

