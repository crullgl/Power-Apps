<h2>Desks List</h2>
<table>
  <thead>
    <tr>
      <th>Column Title</th>
      <th>Column Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><strong>Title</strong></td><td>Single line of text</td><td>Name or identifier of the desk.</td></tr>
    <tr><td><strong>Description</strong></td><td>Multiple lines of text</td><td>Details about the desk, including any unique features.</td></tr>
    <tr><td><strong>Map Link</strong></td><td>Hyperlink or Picture</td><td>Link or image showing the desk’s location on a map.</td></tr>
    <tr><td><strong>Active</strong></td><td>Number</td><td>Indicator (1/0) if the desk is active and available for reservation.</td></tr>
    <tr><td><strong>RoomLocation</strong></td><td>Single line of text</td><td>The room name or number where the desk is located.</td></tr>
    <tr><td><strong>Asset</strong></td><td>Choice</td><td>Asset tag or category assigned to the desk (e.g., Sit/Stand Desk).</td></tr>
    <tr><td><strong>DeskLocation</strong></td><td>Hyperlink or Picture</td><td>Visual or clickable link showing the specific desk location.</td></tr>
    <tr><td><strong>Capacity</strong></td><td>Single line of text</td><td>How many people the desk area can accommodate.</td></tr>
    <tr><td><strong>RoomPicture</strong></td><td>Hyperlink or Picture</td><td>Image or link to a photo of the room where the desk resides.</td></tr>
    <tr><td><strong>Division</strong></td><td>Choice</td><td>Department or organizational unit responsible for the desk.</td></tr>
    <tr><td><strong>POC</strong></td><td>Person or Group</td><td>Primary contact person for desk-related questions or issues.</td></tr>
    <tr><td><strong>VTel</strong></td><td>Hyperlink or Picture</td><td>Visual or link to video teleconference setup, if available.</td></tr>
    <tr><td><strong>Projector/TV</strong></td><td>Hyperlink or Picture</td><td>Link or image showing if the room has a projector or TV.</td></tr>
    <tr><td><strong>SmartBoard</strong></td><td>Hyperlink or Picture</td><td>Link or image showing availability of a smart board.</td></tr>
    <tr><td><strong>SecondPOC</strong></td><td>Person or Group</td><td>Backup contact for desk/room inquiries.</td></tr>
  </tbody>
</table>

<h2>DeskAccessControl List</h2>
<table>
  <thead>
    <tr>
      <th>Column Title</th>
      <th>Column Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><strong>Admin</strong></td><td>Person or Group</td><td>People allowed to manage desk reservations and modify settings.</td></tr>
  </tbody>
</table>

<h2>DeskReservations List</h2>
<table>
  <thead>
    <tr>
      <th>Column Title</th>
      <th>Column Type</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><strong>Title</strong></td><td>Single line of text</td><td>Reservation name or title.</td></tr>
    <tr><td><strong>DeskText</strong></td><td>Single line of text</td><td>Name or label of the reserved desk.</td></tr>
    <tr><td><strong>Reserved By</strong></td><td>Person or Group</td><td>User who booked the desk.</td></tr>
    <tr><td><strong>Check Out From</strong></td><td>Date and Time</td><td>Start date and time for the reservation.</td></tr>
    <tr><td><strong>Check Out To</strong></td><td>Date and Time</td><td>End date and time for the reservation.</td></tr>
    <tr><td><strong>Check Out From Text</strong></td><td>Single line of text</td><td>Formatted text version of Check Out From.</td></tr>
    <tr><td><strong>Check Out To Text</strong></td><td>Single line of text</td><td>Formatted text version of Check Out To.</td></tr>
    <tr><td><strong>Check Out From Number</strong></td><td>Number</td><td>Numeric timestamp for sorting or calculations.</td></tr>
    <tr><td><strong>Check Out To Number</strong></td><td>Number</td><td>Numeric timestamp for sorting or calculations.</td></tr>
    <tr><td><strong>Manager</strong></td><td>Person or Group</td><td>Supervisor or approver for the reservation.</td></tr>
    <tr><td><strong>Service</strong></td><td>Single line of text</td><td>Department or service making the reservation.</td></tr>
    <tr><td><strong>Description</strong></td><td>Single line of text</td><td>Brief description of the reservation purpose.</td></tr>
    <tr><td><strong>Reason for desk reservation</strong></td><td>Single line of text</td><td>Specific reason or need for the desk.</td></tr>
    <tr><td><strong>RoomReservation</strong></td><td>Yes/No</td><td>Indicates if a room was also reserved.</td></tr>
    <tr><td><strong>Asset</strong></td><td>Choice</td><td>Asset type selected for the reservation.</td></tr>
    <tr><td><strong>DeskFloor</strong></td><td>Single line of text</td><td>Floor number or label where desk is located.</td></tr>
    <tr><td><strong>IsRecurring</strong></td><td>Yes/No</td><td>Whether the reservation repeats over time.</td></tr>
    <tr><td><strong>RecurrenceFrequency</strong></td><td>Choice</td><td>How often the reservation recurs (e.g., Weekly).</td></tr>
    <tr><td><strong>RecurrenceEndDate</strong></td><td>Date and Time</td><td>Final date of the recurring reservation series.</td></tr>
    <tr><td><strong>RecurrencePattern</strong></td><td>Choice</td><td>Pattern type (Daily, Weekly, Monthly).</td></tr>
    <tr><td><strong>RecurrenceID</strong></td><td>Number</td><td>ID assigned to a recurrence series.</td></tr>
    <tr><td><strong>ParentReservationID</strong></td><td>Lookup</td><td>Reference to original (parent) reservation for grouped entries.</td></tr>
    <tr><td><strong>Meeting Category</strong></td><td>Choice</td><td>Type of meeting (e.g., Training, Briefing, Private Work).</td></tr>
  </tbody>
</table>

