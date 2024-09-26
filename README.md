// Перерахування для типу велосипеда
enum BicycleType: String {
    case mountain = "Mountain"
    case road = "Road"
    case hybrid = "Hybrid"
}

// Структура Bicycle
struct Bicycle {
    var brand: String
    var type: BicycleType?
    var numberOfSpeeds: Int?
    
    // Метод для опису велосипеда
    func describeBicycle() {
        var description = "Bicycle brand: \(brand)"
        
        if let type = type {
            description += ", Type: \(type.rawValue)"
        } else {
            description += ", Type: unknown"
        }
        
        if let speeds = numberOfSpeeds {
            description += ", Number of speeds: \(speeds)"
        } else {
            description += ", Number of speeds: unknown"
        }
        
        print(description)
    }
}

// Функція для опису велосипеда
func describeBicycle(bicycle: Bicycle) {
    bicycle.describeBicycle()
}

// Створення масиву велосипедів
let bicycles: [Bicycle] = [
    Bicycle(brand: "Trek", type: .mountain, numberOfSpeeds: 21),
    Bicycle(brand: "Giant", type: .road, numberOfSpeeds: nil),
    Bicycle(brand: "Cannondale", type: nil, numberOfSpeeds: 18)
]

// Виведення інформації про кожен велосипед
for bicycle in bicycles {
    describeBicycle(bicycle: bicycle)
}

// Клас Cyclist
class Cyclist {
    var name: String
    var bicycle: Bicycle?
    
    init(name: String, bicycle: Bicycle?) {
        self.name = name
        self.bicycle = bicycle
    }
    
    // Метод для виведення інформації про велосипед велосипедиста
    func describeCyclistBicycle() {
        if let bicycle = bicycle {
            print("\(name)'s bicycle:")
            bicycle.describeBicycle()
        } else {
            print("\(name) does not have a bicycle.")
        }
    }
}

// Приклад використання класу Cyclist
let cyclist1 = Cyclist(name: "Andriy", bicycle: bicycles[0])
let cyclist2 = Cyclist(name: "Oksana", bicycle: nil)

cyclist1.describeCyclistBicycle()
cyclist2.describeCyclistBicycle()
