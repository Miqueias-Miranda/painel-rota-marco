<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Rota - Marco Antonio (Petrópolis / Caxias)</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
  <style>
    body {
      margin: 0; font-family: 'Inter', sans-serif; background-color: #121212; color: #f0f0f0;
    }
    header {
      background-color: #1e1e1e; padding: 1rem; text-align: center;
    }
    h1 { margin: 0; font-size: 1.5rem; }
    #map {
      height: 80vh;
      width: 100%;
    }
    .button-link {
      display: block;
      margin: 1rem auto;
      width: fit-content;
      padding: 0.75rem 1.5rem;
      background-color: #00b894;
      color: white;
      text-decoration: none;
      border-radius: 8px;
      font-weight: bold;
    }
  </style>
</head>
<body>
  <header>
    <h1>📦 Rota Marco Antonio – Petrópolis / Caxias</h1>
  </header>

  <a class="button-link" href="https://maps.app.goo.gl/neEiFiuFWkJ4UtLZ6" target="_blank">📍 Ver localização em tempo real</a>

  <div id="map"></div>

  <script>
    function initMap() {
      const map = new google.maps.Map(document.getElementById("map"), {
        zoom: 10,
        center: { lat: -22.5317904, lng: -43.1760453 },
        mapId: 'a3b0f9384d8f511d'
      });

      const pontos = [
        { nome: "CATEDRAL MATERIAIS DE CONSTRUCAO LTDA", lat: -22.5317904, lng: -43.1760453 }
      ];

      pontos.forEach((ponto, index) => {
        new google.maps.Marker({
          position: { lat: ponto.lat, lng: ponto.lng },
          map,
          title: ponto.nome,
          label: ${index + 1},
        });
      });
    }
  </script>
  <script async defer
    src="https://maps.googleapis.com/maps/api/js?key=SUA_CHAVE_AQUI&callback=initMap">
  </script>
</body>
</html>
