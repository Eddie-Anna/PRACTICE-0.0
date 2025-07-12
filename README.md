    calendar
    just testing how to add, view, and delete events

    events = {}  # date: list of events

    def add_event(date, title):
    if date not in events:
        events[date] = []
    events[date].append(title)
    print(f"Added event '{title}' to {date}")

    def view_events(date):
    if date in events:
        print(f"Events on {date}:")
        for i, e in enumerate(events[date]):
            print(f"{i+1}. {e}")
    else:
        print("No events on this date.")

     def delete_event(date, index):
    try:
        removed = events[date].pop(index - 1)
        print(f"Deleted '{removed}' from {date}")
         if not events[date]:
         
     del events[date]  # remove date key if no events left
   
    except
         print("Something went wrong... maybe invalid index?")
         
     while True:
    print("\n--- Calendar Menu ---")
    print("1. Add event")
    print("2. View events")
    print("3. Delete event")
    print("4. Show all events")
    print("5. Exit")

    choice = input("Pick an option: ")

    if choice == "1":
        d = input("Enter date (e.g. 2025-07-12): ")
        t = input("Event title: ")
        add_event(d, t)

    elif choice == "2":
        d = input("Date to view: ")
        view_events(d)

    elif choice == "3":
        d = input("Date of event: ")
        view_events(d)
        try:
            i = int(input("Which number to delete?: "))
            delete_event(d, i)
        except:
            print("Bad input :/")

    elif choice == "4":
        print("=== All Events ===")
        for day in events:
            print(f"{day}: {events[day]}")

    elif choice == "5":
        print("bye")
        break

    else:
        print("Invalid choice... try again.")
