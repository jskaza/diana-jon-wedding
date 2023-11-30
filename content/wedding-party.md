+++
title="Wedding Party"
+++

<div style="text-align: center">
<b>Andrew Skaza</b><br>
<i>Best Man</i><br>
<i>Brother of the Groom</i>

<b>Celena Kellerman</b><br>
<i>Matron of Honor</i><br>
<i>Cousin of the Bride</i>

<b>Michael Skaza</b><br>
<i>Groomsman</i><br>
<i>Brother of the Groom</i>

<b>Dorisanne Wonsor</b><br>
<i>Bridesmaid</i><br>
<i>Friend of the Bride</i>
</div>


<style>
label {
display: block;
margin-bottom: 10px;
}
</style>
</head>
<body>

<h1>Wedding RSVP Form</h1>

<form action="#" method="post">

<label for="name">Your Name:</label>
<select id="name" name="name" oninput="updateGuests()" required>
<option value="" disabled selected>Select your name</option>
<!-- Add your list of names here -->
<option value="John Doe">John Doe</option>
<option value="Jane Smith">Jane Smith</option>
<option value="Bob Johnson">Bob Johnson</option>
<!-- Add more names as needed -->
</select>

<label for="attendance">Will you be attending?</label>
<select id="attendance" name="attendance" required>
<option value="yes">Yes</option>
<option value="no">No</option>
</select>

<div id="guests-container">
<!-- Guest details will be dynamically added here -->
</div>

<button type="submit">Submit RSVP</button>

</form>

<script>
const guestsMapping = {
'John Doe': 2,   // John Doe has 2 associated guests
'Jane Smith': 1, // Jane Smith has 1 associated guest
'Bob Johnson': 3 // Bob Johnson has 3 associated guests
// Add more names and associated guest counts as needed
};

function updateGuests() {
const selectedName = document.getElementById('name').value;
const guestsContainer = document.getElementById('guests-container');
guestsContainer.innerHTML = ''; // Clear previous guests

if (selectedName && guestsMapping[selectedName]) {
    const guestCount = guestsMapping[selectedName];

    for (let i = 1; i <= guestCount; i++) {
        const guestDiv = document.createElement('div');
        guestDiv.classList.add('guest');

        const nameLabel = document.createElement('label');
        nameLabel.textContent = `Name of Guest ${i}:`;
        guestDiv.appendChild(nameLabel);

        const nameInput = document.createElement('input');
        nameInput.type = 'text';
        nameInput.name = `guest-${i}-name`;
        nameInput.required = true;
        nameInput.value = ''; // Clear previous values
        guestDiv.appendChild(nameInput);

        const mealLabel = document.createElement('label');
        mealLabel.textContent = `Meal Choice for Guest ${i}:`;
        guestDiv.appendChild(mealLabel);

        const mealInput = document.createElement('input');
        mealInput.type = 'text';
        mealInput.name = `guest-${i}-meal`;
        mealInput.required = true;
        guestDiv.appendChild(mealInput);

        guestsContainer.appendChild(guestDiv);
    }
}
}
</script>