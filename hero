class GameCharacter:
    def __init__(self, name, health, attack_power, defense):
        self.name = name
        self.health = health
        self.max_health = health 
        self.attack_power = attack_power
        self.level = 1
        self.defense = defense

    def attack(self, target):
        print(f"{self.name} атакує {target.name} з силою {self.attack_power}!")
        target.take_damage(self.attack_power)

    def take_damage(self, damage):
        actual_damage = max(damage - self.defense, 0)
        self.health -= actual_damage
        if self.health < 0:
            self.health = 0
        print(f"{self.name} отримав {actual_damage} пошкоджень. "
              f"Здоров'я: {self.health}/{self.max_health}")

        if self.health == 0:
            print(f"{self.name} помер!")

    def is_alive(self):
        return self.health > 0

    def level_up(self):
        self.level += 1
        self.max_health += 10
        self.health = self.max_health  
        self.attack_power += 5
        self.defense += 2
        print(f"{self.name} піднявся до {self.level} рівня!")

    def get_info(self):
        status = "живий" if self.is_alive() else "мертвий"
        print(f"Персонаж: {self.name} ({status})")
        print(f"Рівень: {self.level}")
        print(f"Здоров'я: {self.health}/{self.max_health}")
        print(f"Сила атаки: {self.attack_power}")
        print(f"Захист: {self.defense}")


hero = GameCharacter("Белегар", 100, 20, 10)
enemy = GameCharacter("Горбак", 120, 15, 3)

hero.get_info()
enemy.get_info()

print("\nПочаток бою")



# Бій триває, поки обидва живі
while hero.is_alive() and enemy.is_alive():
    hero.attack(enemy)
    if enemy.is_alive():
        enemy.attack(hero)

print("\nБій закінчено")

hero.level_up()

print("\nПісля підвищення рівня")
hero.get_info()
