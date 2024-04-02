# dental
class DentalOffice:
    def __init__(self):
        self.schedule = {}

    def schedule_appointment(self, date, time, patient_name):
        if date in self.schedule:
            if time in self.schedule[date]:
                print(f"Appointment already scheduled at {time} on {date}.")
            else:
                self.schedule[date][time] = patient_name
        else:
            self.schedule[date] = {time: patient_name}
        print(f"Appointment scheduled for {patient_name} at {time} on {date}.")

    def display_schedule(self):
        if not self.schedule:
            print("No appointments scheduled.")
        else:
            print("Dental Office Schedule:")
            for date, appointments in self.schedule.items():
                print(f"On {date}:")
                for time, patient_name in appointments.items():
                    print(f"    - {time}: {patient_name}")


def main():
    dental_office = DentalOffice()

    dental_office.schedule_appointment("2024-04-03", "09:00", "John Doe")
    dental_office.schedule_appointment("2024-04-03", "10:30", "Jane Smith")
    dental_office.schedule_appointment("2024-04-05", "11:00", "Alice Johnson")
    dental_office.schedule_appointment("2024-04-07", "14:00", "Bob Brown")

    dental_office.display_schedule()


if __name__ == "__main__":
    main()
