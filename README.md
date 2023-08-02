

def get_weather_data(date):
    url = f"https://api.example.com/weather?date={date}"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        return data['temperature']
    else:
        return None

def get_wind_speed_data(date):
    url = f"https://api.example.com/wind-speed?date={date}"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        return data['wind']['speed']
    else:
        return None

def get_pressure_data(date):
    url = f"https://api.example.com/pressure?date={date}"
    response = requests.get(url)
    if response.status_code == 200:
        data = response.json()
        return data['pressure']
    else:
        return None
def main():
    while True:
        print("1. Get weather")
        print("2. Get Wind Speed")
        print("3. Get Pressure")
        print("0. Exit")

        option = int(input("Enter your choice: "))

        if option == 1:
            date = input("Enter the date (YYYY-MM-DD): ")
            temperature = get_weather_data(date)
            if temperature is not None:
                print(f"Temperature on {date}: {temperature}°C")
            else:
                print("Data not available for the given date.")
        elif option == 2:
            date = input("Enter the date (YYYY-MM-DD): ")
            wind_speed = get_wind_speed_data(date)
            if wind_speed is not None:
                print(f"Wind Speed on {date}: {wind_speed} km/h")
            else:
                print("Data not available for the given date.")
        elif option == 3:
            date = input("Enter the date (YYYY-MM-DD): ")
            pressure = get_pressure_data(date)
            if pressure is not None:
                print(f"Pressure on {date}: {pressure} hPa")
            else:
                print("Data not available for the given date.")
        elif option == 0:
            break
        else:
            print("Invalid option. Please try again.")

if __name__ == "_main_":
    main()
