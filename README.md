# crimewatchx
“A platform where people can learn about offenders being released in their area, including brief information about their history — helping communities stay safe.” Meow
<!DOCTYPE html>
<html>
<head>
    <title>CrimeWatch</title>

    <style>
        body {
            margin: 0;
            font-family: Arial;
            background: #0d0d0d;
            color: white;
        }

        header {
            background: #111;
            padding: 15px;
            text-align: center;
            font-size: 24px;
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            padding: 20px;
        }

        .card {
            background: #1a1a1a;
            border-radius: 10px;
            overflow: hidden;
            cursor: pointer;
            transition: 0.3s;
        }

        .card img {
            width: 100%;
            height: 160px;
            object-fit: cover;
        }

        .card-content {
            padding: 10px;
        }

        .card:hover {
            transform: scale(1.05);
        }

        /* MODAL */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.8);
        }

        .modal-content {
            background: #111;
            margin: 5% auto;
            padding: 20px;
            width: 60%;
            border-radius: 10px;
        }

        .modal img {
            width: 100%;
            border-radius: 10px;
            margin-bottom: 10px;
        }

        .close {
            float: right;
            cursor: pointer;
            font-size: 20px;
        }

    </style>
</head>

<body>

<header>🔎 CrimeWatch</header>

<div class="cards">

    <div class="card" onclick="openModal(
        'Sprawa A',
        'Polska',
        'zabójstwo',
        'Znana sprawa z 2010 roku...',
        'https://images.unsplash.com/photo-1544717305-2782549b5136'
    )">
        <img src="https://images.unsplash.com/photo-1544717305-2782549b5136">
        <div class="card-content">
            <h2>Sprawa A</h2>
            <p>📍 Polska</p>
        </div>
    </div>

    <div class="card" onclick="openModal(
        'Sprawa B',
        'Niemcy',
        'oszustwo',
        'Głośna sprawa finansowa...',
        'https://images.unsplash.com/photo-1505666287802-931dc83a9c1b'
    )">
        <img src="https://images.unsplash.com/photo-1505666287802-931dc83a9c1b">
        <div class="card-content">
            <h2>Sprawa B</h2>
            <p>📍 Niemcy</p>
        </div>
    </div>

</div>

<!-- MODAL -->
<div id="modal" class="modal">
    <div class="modal-content">
        <span class="close" onclick="closeModal()">✖</span>

        <img id="modal-img">

        <h2 id="title"></h2>
        <p id="location"></p>
        <p id="type"></p>
        <p id="description"></p>
    </div>
</div>

<script>

function openModal(title, location, type, description, image) {
    document.getElementById("modal").style.display = "block";

    document.getElementById("title").innerText = title;
    document.getElementById("location").innerText = "📍 " + location;
    document.getElementById("type").innerText = "⚖️ " + type;
    document.getElementById("description").innerText = description;
    document.getElementById("modal-img").src = image;
}

function closeModal() {
    document.getElementById("modal").style.display = "none";
}

</script>

</body>
</html>
