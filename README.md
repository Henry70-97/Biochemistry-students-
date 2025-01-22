<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Biochemistry</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f9;
            color: #333;
            margin: 0;
            padding: 0;
        }
        header {
            background-color: #4CAF50;
            color: white;
            text-align: center;
            padding: 1em 0;
        }
        main {
            padding: 20px;
            max-width: 800px;
            margin: 0 auto;
        }
        section {
            margin-bottom: 20px;
            padding: 10px;
            background: #fff;
            border: 1px solid #ddd;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }
        h2 {
            margin-top: 0;
        }
        textarea {
            width: 100%;
            height: 150px;
            margin: 10px 0;
            padding: 10px;
            font-size: 14px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        button {
            padding: 10px 20px;
            background-color: #4CAF50;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        button:hover {
            background-color: #45a049;
        }
    </style>
</head>
<body>
    <header>
        <h1>Biochemistry</h1>
        <p>Store your notes for various subjects.</p>
    </header>
    <main>
        <section id="organic-chemistry">
            <h2>Organic Chemistry</h2>
            <textarea id="notes-organic"></textarea>
            <button onclick="saveNotes('organic')">Save Notes</button>
        </section>
        <section id="bmet-111">
            <h2>BMET 111</h2>
            <textarea id="notes-bmet111"></textarea>
            <button onclick="saveNotes('bmet111')">Save Notes</button>
        </section>
        <section id="bmet-110">
            <h2>BMET 110</h2>
            <textarea id="notes-bmet110"></textarea>
            <button onclick="saveNotes('bmet110')">Save Notes</button>
        </section>
        <section id="coms-100">
            <h2>COMS 100</h2>
            <textarea id="notes-coms"></textarea>
            <button onclick="saveNotes('coms')">Save Notes</button>
        </section>
    </main>
    <script>
        // Save notes to localStorage
        function saveNotes(subject) {
            const notes = document.getElementById(`notes-${subject}`).value;
            localStorage.setItem(`notes-${subject}`, notes);
            alert('Notes saved!');
        }

        // Load saved notes on page load
        document.addEventListener('DOMContentLoaded', () => {
            ['organic', 'bmet111', 'bmet110', 'coms'].forEach(subject => {
                const savedNotes = localStorage.getItem(`notes-${subject}`);
                if (savedNotes) {
                    document.getElementById(`notes-${subject}`).value = savedNotes;
                }
            });
        });
    </script>
</body>
</html>
