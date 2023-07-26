
def get_weather_data(date):
    weather_data = {
        "2023-07-20": {"temp": 31, "wind_speed": 2, "pressure": 1011},
        "2023-07-21": {"temp": 32, "wind_speed": 3, "pressure": 1012},
        "2023-07-22": {"temp": 38, "wind_speed": 4, "pressure": 1013},
        "2023-07-23": {"temp": 33, "wind_speed": 5, "pressure": 1014},
        "2023-07-24": {"temp": 34, "wind_speed": 7, "pressure": 1016},
        "2023-07-25": {"temp": 28, "wind_speed": 10, "pressure": 1015},
        "2023-07-26": {"temp": 30, "wind_speed": 8, "pressure": 1010},
    }
    return weather_data.get(date)

def get_option():
    print("1. Get weather")
    print("2. Get Wind Speed")
    print("3. Get Pressure")
    print("0. Exit")
    return int(input("Enter your choice: "))

def get_date_input():
    return input("Enter the date (YYYY-MM-DD): ")

def get_temp(date):
    weather_data = get_weather_data(date)
    if weather_data:
        return weather_data["temp"]
    else:
        return None

def get_wind_speed(date):
    weather_data = get_weather_data(date)
    if weather_data:
        return weather_data["wind_speed"]
    else:
        return None

def get_pressure(date):
    weather_data = get_weather_data(date)
    if weather_data:
        return weather_data["pressure"]
    else:
        return None

def main():
    while True:
        option = get_option()

        if option == 1:
            date = get_date_input()
            temp = get_temp(date)
            if temp is not None:
                print(f"Temperature on {date}: {temp}°C")
            else:
                print("No data available for the specified date.")
        elif option == 2:
            date = get_date_input()
            wind_speed = get_wind_speed(date)
            if wind_speed is not None:
                print(f"Wind Speed on {date}: {wind_speed} km/h")
            else:
                print("No data available for the specified date.")
        elif option == 3:
            date = get_date_input()
            pressure = get_pressure(date)
            if pressure is not None:
                print(f"Pressure on {date}: {pressure} hPa")
            else:
                print("No data available for the specified date.")
        elif option == 0:
            print("Exiting the program.")
            break
        else:
            print("Invalid option. Please try again.")

if __name__ == "__main__":
    main()
