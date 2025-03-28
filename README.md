# OPERATORI
#Программа 1: Конвертация температуры

#include <iostream>

float celsiusToFahrenheit(float celsius) {
    return (celsius * 9.0 / 5.0) + 32.0;
}

float fahrenheitToCelsius(float fahrenheit) {
    return (fahrenheit - 32.0) * 5.0 / 9.0;
}

int main() {
    float celsius, fahrenheit;

    std::cout << "Введите температуру в градусах Цельсия: ";
    std::cin >> celsius;
    fahrenheit = celsiusToFahrenheit(celsius);
    std::cout << "Температура в градусах Фаренгейта: " << static_cast<int>(fahrenheit) << "°F" << std::endl;

    std::cout << "Введите температуру в градусах Фаренгейта: ";
    std::cin >> fahrenheit;
    celsius = fahrenheitToCelsius(fahrenheit);
    std::cout << "Температура в градусах Цельсия: " << static_cast<int>(celsius) << "°C" << std::endl;

    return 0;
}

#Программа 2: Автопарк с легковыми и грузовыми автомобилями

#include <iostream>
#include <vector>
#include <memory>

class Vehicle {
public:
    virtual void displayType() const = 0; // Чисто виртуальная функция
    virtual ~Vehicle() {}
};

class Car : public Vehicle {
public:
    void displayType() const override {
        std::cout << "Это легковой автомобиль." << std::endl;
    }
};

class Truck : public Vehicle {
public:
    void displayType() const override {
        std::cout << "Это грузовой автомобиль." << std::endl;
    }
};

int main() {
    std::vector<std::unique_ptr<Vehicle>> fleet;

    fleet.push_back(std::make_unique<Car>());
    fleet.push_back(std::make_unique<Truck>());
    fleet.push_back(std::make_unique<Car>());

    std::cout << "Автопарк содержит следующие автомобили:" << std::endl;
    for (const auto& vehicle : fleet) {
        vehicle->displayType();
    }

    return 0;
}

Найти еще
