<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Matemáticas en AR</title>
    <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
    <script src="https://cdn.rawgit.com/jeromeetienne/ar.js/1.7.2/aframe/build/aframe-ar.min.js"></script>
</head>
<body style="margin: 0; overflow: hidden;">
    <a-scene embedded arjs>
        <!-- Cámara AR -->
        <a-marker preset="hiro">
            <!-- Bloque con número 3 -->
            <a-box position="-0.3 0 0" material="color: red"></a-box>
            <a-text value="3" position="-0.3 0.5 0" align="center" color="white"></a-text>

            <!-- Bloque con número 2 -->
            <a-box position="0.3 0 0" material="color: blue"></a-box>
            <a-text value="2" position="0.3 0.5 0" align="center" color="white"></a-text>
        </a-marker>

        <a-entity camera></a-entity>
    </a-scene>

    <!-- Interfaz para ingresar la respuesta -->
    <div style="position: fixed; bottom: 20px; left: 50%; transform: translateX(-50%); text-align: center;">
        <input type="number" id="respuesta" placeholder="¿Cuánto es 3 + 2?" style="padding: 10px; font-size: 18px;">
        <button onclick="verificarRespuesta()" style="padding: 10px; font-size: 18px;">Verificar</button>
        <p id="mensaje" style="font-size: 20px; font-weight: bold;"></p>
    </div>

    <script>
        function verificarRespuesta() {
            let respuesta = document.getElementById("respuesta").value;
            let mensaje = document.getElementById("mensaje");
            if (respuesta == 5) {
                mensaje.textContent = "¡Correcto!";
                mensaje.style.color = "green";
            } else {
                mensaje.textContent = "Incorrecto. La respuesta es 5.";
                mensaje.style.color = "red";
            }
        }
    </script>
</body>
</html>
