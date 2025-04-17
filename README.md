<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Compartilhar Localização</title>
</head>
<body>
  <h2>Clique no botão para compartilhar sua localização</h2>
  <button onclick="getLocation()">Compartilhar</button>

  <script>
    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(sendLocation, showError);
      } else {
        alert("Seu navegador não suporta geolocalização.");
      }
    }

    function sendLocation(position) {
      const lat = position.coords.latitude;
      const lon = position.coords.longitude;
      const link = `https://wa.me/5591991239984?text=Minha%20localização:%20https://www.google.com/maps?q=${lat},${lon}`;
      window.location.href = link;
    }

    function showError(error) {
      alert("Não foi possível obter a localização.");
    }
  </script>
</body>
</html>