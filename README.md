<!DOCTYPE html>
<html>
<head>
    <title>Cuentas regresivas</title>

    <style>
        body {
            font-family: Arial;
            background-color: #f0f8ff;
            text-align: center;
            padding: 20px;
        }

        .seccion {
            border-bottom: 2px solid #ccc;
            padding: 20px;
            margin-bottom: 10px;
        }

        h2 {
            color: #F7E7CE;
        }

        .contador {
            font-size: 28px;
            margin-top: 10px;
        }
    </style>
</head>

<body>

    <h1>🥳🎉 Cuentas regresivas 🥳🎉</h1>

    <div class="seccion">
        <h2>Maylen</h2>
        <p>📅 ❤️8 de marzo❤️</p>
        <div class="contador" id="maylen"></div>
    </div>

    <div class="seccion">
        <h2>Karina</h2>
        <p>📅 🤩2 de abril🤩</p>
        <div class="contador" id="karina"></div>
    </div>

    <div class="seccion">
        <h2>Juliana</h2>
        <p>📅 😍7 de abril😍</p>
        <div class="contador" id="juliana"></div>
    </div>

    <div class="seccion">
        <h2>Marcelo</h2>
        <p>📅 💜10 de junio💜</p>
        <div class="contador" id="marcelo"></div>
    </div>

    <script>
        function cuentaRegresiva(fechaObjetivo, idElemento) {
            setInterval(function () {
                var ahora = new Date().getTime();
                var diferencia = fechaObjetivo - ahora;

                if (diferencia < 0) {
                    document.getElementById(idElemento).innerHTML = "🎂 ¡Hoy es el día!";
                    return;
                }

                var dias = Math.floor(diferencia / (1000 * 60 * 60 * 24));
                var horas = Math.floor((diferencia % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                var minutos = Math.floor((diferencia % (1000 * 60 * 60)) / (1000 * 60));
                var segundos = Math.floor((diferencia % (1000 * 60)) / 1000);

                document.getElementById(idElemento).innerHTML =
                    dias + "d " + horas + "h " + minutos + "m " + segundos + "s";
            }, 1000);
        }

        cuentaRegresiva(new Date("March 8, 2026 00:00:00").getTime(), "maylen");
        cuentaRegresiva(new Date("April 2, 2026 00:00:00").getTime(), "karina");
        cuentaRegresiva(new Date("April 7, 2026 00:00:00").getTime(), "juliana");
        cuentaRegresiva(new Date("June 10, 2026 00:00:00").getTime(), "marcelo");
    </script>

</body>
</html>
