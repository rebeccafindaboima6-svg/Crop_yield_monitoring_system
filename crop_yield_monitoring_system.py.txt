
class Farmer:
    def __init__(self, farmer_id, name, location):
        self.farmer_id = farmer_id
        self.name = name
        self.location = location

    def display_info(self):
        print(f"Farmer ID: {self.farmer_id}")
        print(f"Farmer Name: {self.name}")
        print(f"Location: {self.location}")


class CropRecord:
    """Store one crop record and calculate its yield performance."""

    total_records = 0

    def __init__(
        self, record_id, farmer, crop_name, farm_size,
        expected_yield, actual_yield
    ):
        if farm_size <= 0:
            raise ValueError("Farm size must be greater than zero.")

        if expected_yield < 0 or actual_yield < 0:
            raise ValueError("Yield amounts cannot be negative.")

        self.record_id = record_id
        self.farmer = farmer
        self.crop_name = crop_name
        self.farm_size = farm_size
        self.expected_yield = expected_yield
        self.actual_yield = actual_yield

        CropRecord.total_records += 1

    def calculate_performance(self):
        """Calculate actual yield as a percentage of expected yield."""
        if self.expected_yield == 0:
            return 0

        return (self.actual_yield / self.expected_yield) * 100

    def update_record(self, actual_yield):
        """Update the actual yield after validation."""
        if not self.is_valid_yield(actual_yield):
            raise ValueError("Actual yield cannot be negative.")

        self.actual_yield = actual_yield

    def display_info(self):
        performance = self.calculate_performance()

        print("----------------------------------------")
        print(f"Record ID: {self.record_id}")
        print(f"Farmer ID: {self.farmer.farmer_id}")
        print(f"Farmer: {self.farmer.name}")
        print(f"Location: {self.farmer.location}")
        print(f"Crop: {self.crop_name}")
        print(f"Farm Size: {self.farm_size:.2f} acres")
        print(f"Expected Yield: {self.expected_yield:.2f} kg")
        print(f"Actual Yield: {self.actual_yield:.2f} kg")
        print(f"Yield Performance: {performance:.2f}%")
        print("----------------------------------------")

    @classmethod
    def get_total_records(cls):
        """Return the total records created during this session."""
        return cls.total_records

    @staticmethod
    def is_valid_yield(yield_amount):
        """Check that a yield amount is zero or greater."""
        return yield_amount >= 0


def add_crop_record(crop_records):
    print("\nADD NEW CROP RECORD")

    record_id = input("Enter record ID: ").strip()
    farmer_id = input("Enter farmer ID: ").strip()
    farmer_name = input("Enter farmer name: ").strip()
    location = input("Enter farm location: ").strip()
    crop_name = input("Enter crop name: ").strip()

    if not all([
        record_id, farmer_id, farmer_name, location, crop_name
    ]):
        print("Please complete all text fields.")
        return

    try:
        farm_size = float(input("Enter farm size in acres: "))
        expected_yield = float(input("Enter expected yield in kg: "))
        actual_yield = float(input("Enter actual yield in kg: "))
    except ValueError:
        print("Invalid input. Enter numbers for farm size and yield.")
        return

    if farm_size <= 0:
        print("Farm size must be greater than zero.")
        return

    if not CropRecord.is_valid_yield(expected_yield):
        print("Expected yield cannot be negative.")
        return

    if not CropRecord.is_valid_yield(actual_yield):
        print("Actual yield cannot be negative.")
        return

    farmer = Farmer(farmer_id, farmer_name, location)

    record = CropRecord(
        record_id,
        farmer,
        crop_name,
        farm_size,
        expected_yield,
        actual_yield
    )

    crop_records.append(record)
    print("\nCrop record added successfully.")


def display_records(crop_records):
    if len(crop_records) == 0:
        print("\nNo crop records available.")
        return

    print("\nCROP YIELD RECORDS")

    for record in crop_records:
        record.display_info()


def main():
    crop_records = []

    while True:
        print("\n===================================")
        print("     CROP YIELD MONITORING SYSTEM")
        print("===================================")
        print("1. Add Crop Record")
        print("2. Display Crop Records")
        print("3. Show Total Records")
        print("4. Exit")

        choice = input("Enter your choice: ").strip()

        if choice == "1":
            add_crop_record(crop_records)

        elif choice == "2":
            display_records(crop_records)

        elif choice == "3":
            print(
                f"\nTotal crop records: "
                f"{CropRecord.get_total_records()}"
            )

        elif choice == "4":
            print(
                "\nThank you for using the Crop Yield Monitoring System."
            )
            break

        else:
            print("\nInvalid choice. Please select 1, 2, 3 or 4.")


if __name__ == "__main__":
    main()
