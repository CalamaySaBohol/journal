<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Journaling</title>
    <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="min-h-screen flex flex-col items-center bg-gray-100 p-6">

    <!-- Navigation -->
    <nav class="bg-white shadow-md py-4 px-6 flex justify-between items-center w-full">
        <a href="https://vitejsvitencgxp6j8-dosp--5173--495c5120.local-corp.webcontainer.io" class="text-gray-700 font-semibold hover:text-blue-600">⬅ Back to Home</a>
    </nav>

    <!-- Journaling Section -->
    <div class="bg-white p-6 rounded-2xl shadow-lg max-w-xl mt-10 w-full">
        <h2 class="text-2xl font-bold text-center mb-6">Daily Journal</h2>

        <!-- Question -->
        <p class="text-lg font-semibold text-gray-700 mb-2">What's on your mind today?</p>

        <!-- Journal Entry Input -->
        <textarea id="journalEntry" class="w-full p-4 border border-gray-300 rounded-lg" rows="6" placeholder="Write your thoughts here..."></textarea>
        
        <div class="text-center mt-4">
            <button onclick="saveEntry()" class="bg-blue-600 text-white px-6 py-2 rounded-lg hover:bg-blue-700">Save Entry</button>
        </div>

        <!-- Previous Entries Section -->
        <div class="mt-6">
            <h3 class="text-lg font-semibold">Previous Entries:</h3>
            <ul id="journalList" class="mt-2 space-y-2"></ul>
        </div>
    </div>

    <script>
        function saveEntry() {
            let entry = document.getElementById("journalEntry").value;
            if (entry.trim() === "") {
                alert("Please write something before saving.");
                return;
            }

            let journalList = document.getElementById("journalList");
            let listItem = document.createElement("li");
            listItem.className = "p-3 bg-gray-200 rounded-lg";
            listItem.textContent = entry;
            
            journalList.appendChild(listItem);
            document.getElementById("journalEntry").value = "";
        }
    </script>

</body>
</html>
