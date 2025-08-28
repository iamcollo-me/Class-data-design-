class Vehicle:
    def __init__(self, brand="Generic", model="Vehicle", year=None):
        self.brand = brand
        self.model = model
        self.year = year
    
    def start(self):
        print(f"{self.brand} {self.model} is starting...")

    def stop(self):
        print(f"{self.brand} {self.model} is stopping...")

    def move(self):
        print("Vehicle is moving")

# Polymorphism: Each vehicle defines move() differently
class Car(Vehicle):
    def __init__(self, brand, model, year):
        super().__init__(brand, model, year)
    
    def move(self):
        print("Driving 🚗")

class Plane(Vehicle):
    def __init__(self, brand, model, year):
        super().__init__(brand, model, year)
    
    def move(self):
        print("Flying ✈️")

class Boat(Vehicle):
    def __init__(self, brand, model, year):
        super().__init__(brand, model, year)
    
    def move(self):
        print("Sailing 🛥️")

# Your custom Mercedes Benz GLE class
class MercedesBenzGLE(Car):
    def __init__(self, year, color, engine_type):
        super().__init__("Mercedes-Benz", "GLE", year)
        self.color = color
        self.engine_type = engine_type

    def drive_mode(self, mode):
        print(f"{self.brand} {self.model} is now in {mode} mode.")

    def display_info(self):
        print(f"Mercedes-Benz GLE ({self.year}) - Color: {self.color}, Engine: {self.engine_type}")

# Example usage for Mercedes Benz GLE
gle1 = MercedesBenzGLE(2023, "Black", "V6 Turbo")
gle1.start()
gle1.drive_mode("Sport")
gle1.display_info()
gle1.move()  # Will print "Driving 🚗" because it's a Car
gle1.stop()

print("\nPolymorphism Demo:")
# Polymorphism demonstration
vehicles = [
    Car("Toyota", "Corolla", 2022),
    Plane("Boeing", "747", 2019),
    Boat("Yamaha", "212X", 2021),
    gle1  # MercedesBenzGLE also behaves as a Car
]

for v in vehicles:
    v.move()# Class-data-design-
