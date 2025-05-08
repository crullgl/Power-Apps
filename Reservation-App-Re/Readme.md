# 🪑 Desk Reservation Power App Documentation

This Power Platform app allows users to reserve desks and rooms, including support for **recurring reservations**. Below is an overview of the app’s data structure, recurrence logic, and key user interactions.

---

## 📋 SharePoint Lists

### **Desks List**
| Column Title     | Column Type          | Description |
|------------------|----------------------|-------------|
| Title            | Single line of text  | Desk identifier or label. |
| Description      | Multiple lines of text | Desk details or features. |
| Map Link         | Hyperlink or Picture | Link/image of desk map. |
| Active           | Number               | 1 = active, 0 = inactive. |
| RoomLocation     | Single line of text  | Room where desk is located. |
| Asset            | Choice               | e.g., Sit/Stand Desk. |
| DeskLocation     | Hyperlink or Picture | Desk position visual/link. |
| Capacity         | Single line of text  | Desk capacity. |
| RoomPicture      | Hyperlink or Picture | Room photo. |
| Division         | Choice               | Department or unit. |
| POC              | Person or Group      | Primary desk contact. |
| VTel             | Hyperlink or Picture | V-Tel setup image or link. |
| Projector/TV     | Hyperlink or Picture | Room A/V setup link. |
| SmartBoard       | Hyperlink or Picture | SmartBoard availability. |
| SecondPOC        | Person or Group      | Backup contact. |

---

### **DeskAccessControl List**
| Column Title | Column Type     | Description |
|--------------|------------------|-------------|
| Admin        | Person or Group | People allowed to manage desk settings and reservations. |

---

### **DeskReservations List**
| Column Title             | Column Type         | Description |
|--------------------------|---------------------|-------------|
| Title                    | Single line of text | Reservation title. |
| DeskText                 | Single line of text | Desk label. |
| Reserved By              | Person or Group     | Who made the reservation. |
| Check Out From           | Date and Time       | Start of reservation. |
| Check Out To             | Date and Time       | End of reservation. |
| Check Out From Text      | Single line of text | Formatted start date. |
| Check Out To Text        | Single line of text | Formatted end date. |
| Check Out From Number    | Number              | Start timestamp. |
| Check Out To Number      | Number              | End timestamp. |
| Manager                  | Person or Group     | Reservation approver. |
| Service                  | Single line of text | Requesting department. |
| Description              | Single line of text | Purpose of reservation. |
| Reason for desk reservation | Single line of text | Justification. |
| RoomReservation          | Yes/No              | Is a room also reserved? |
| Asset                    | Choice              | Type of item reserved. |
| DeskFloor                | Single line of text | Floor of reserved desk. |
| IsRecurring              | Yes/No              | Repeats over time? |
| RecurrenceFrequency      | Choice              | How often it recurs. |
| RecurrenceEndDate        | Date and Time       | When recurrence stops. |
| RecurrencePattern        | Choice              | Pattern type (Daily, Weekly, etc.). |
| RecurrenceID             | Number              | Unique series ID. |
| ParentReservationID      | Lookup              | Link to main reservation. |
| Meeting Category         | Choice              | Purpose (Training, Work, etc.). |

---

## 🔁 Recurring Reservation Logic

### 🔹 Steps
1. **Enable Recurring Toggle**: User selects frequency and number of repeats.
2. **Loop Using `Sequence()`**:
   - Generates values like `[0, 1, 2, ...]` based on number of occurrences.
3. **Calculate Dates**:
   - Uses `DateAdd()` and `Switch()` for Daily, Weekly, Bi-Weekly, and Monthly recurrence patterns.
   - Monthly uses modular math to hit the Nth weekday.
4. **Build Collection**:
   - Creates `CollectionRecurrence` with `StartDateTime` and `EndDateTime` based on selected times.
5. **Conflict Detection**:
   - Filters `'Desk Reservations'` list using `LookUp()` to see if any new dates conflict with existing bookings.
   - Conflicts are stored in `colDeskChckRecur`.
6. **Recurrence ID Handling**:
   - All reservations in the same series get the same `RecurrenceID`.
   - The first entry may be used as `ParentReservationID` for easy bulk edits/cancellations.

---

## 🧮 “Continue” Button Logic

When a user selects a date/time and hits the **Continue** button:

1. **Capture Selection**:
   - `selectedDate` and `selectedEndDate` are pulled from the calendar.
   - `startTime` and `endTime` are built by combining the date and time dropdowns.

2. **Adjust for Same-Day or Cross-Day**:
   - If the end date is earlier than the start date, the logic adjusts it to avoid errors.

3. **Conflict Detection**:
   - Creates `colBookedDesks` by filtering for any overlaps in existing reservations.

4. **Expand to Room-Level Assets**:
   - If any reserved item is a Room, it searches the `Desks` list for items within the same room (excluding pure Desks or Items).
   - Adds those to `colBookedDesks`.

5. **Navigation**:
   - App navigates to the `DeskSelect` screen after filtering is done.

6. **Build Room Filter**:
   - Clears `colRoomLocations`.
   - Adds `"All Conference Rms"` as default.
   - Then adds distinct room names from the `Desks` list where the asset is not a desk/item.

---

## 💡 Notes

- Built using Power Apps with SharePoint as the data source.
- Designed for VA and federal workspace reservations.
- Supports both individual and room-level recurring logic.

---

## 📸 UI Preview (Optional)

> _Include screenshots or GIFs of your app’s UI here, if applicable._

---

## 📂 Repo Structure Suggestion

