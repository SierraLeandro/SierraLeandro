<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="./style/index.css">
    <link rel="icon" href="favicon.png" type="image/png">
    <title>Colombia Expediciones</title>
    <style>
        .modal {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.7);
            position: fixed;
            top: 0;
            left: 0;
            z-index: 1000;
        }
        .modal-content {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            width: 300px;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            text-align: center;
        }
        .modal h2 {
            margin: 0 0 20px;
        }
        .modal label {
            margin-top: 10px;
        }
        .modal input {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .modal button {
            margin-top: 15px;
            padding: 10px;
            background-color: #007BFF;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .modal button:hover {
            background-color: #0056b3;
        }
        .close-btn {
            margin-top: 10px;
            background-color: #dc3545;
        }
        .lugares-modal {
            background-color: white;
            padding: 20px;
            border-radius: 10px;
            width: 400px;
            max-height: 80%;
            overflow-y: auto;
            box-shadow: 0 2px 10px rgba(0, 0, 0, 0.3);
            text-align: center;
        }
        .lugares-modal h2 {
            margin-bottom: 15px;
        }
        .lugares-modal ul {
            list-style-type: none;
            padding: 0;
        }
        .lugares-modal li {
            margin: 10px 0;
        }
        .lugares-modal a {
            color: #007BFF;
            text-decoration: none;
        }
        /* Responsive styles */
        @media (max-width: 600px) {
            .modal-content, .lugares-modal {
                width: 90%;
            }
            .actividad-imagen {
                width: 100%;
                height: auto;
            }
        }
    </style>
    <script>
        function resetPage() {
            window.location.reload(); // Recarga la página
        }

        function mostrarLugares() {
            const lugares = `
                <div class="lugares-modal">
                    <h2>Lugares para Conocer</h2>
                    <ul>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=San+Gil" target="_blank" rel="noopener noreferrer">San Gil</a></li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Barichara" target="_blank" rel="noopener noreferrer">Barichara</a></li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Guane" target="_blank" rel="noopener noreferrer">Guane</a></li>
                        <li><a href="https://www.google.com/maps/search/?api=1&query=Cañón+del+Chicamocha" target="_blank" rel="noopener noreferrer">Cañón del Chicamocha</a></li>
                    </ul>
                    <button onclick="cerrarLugares()">Cerrar</button>
                </div>
            `;
            crearModal(lugares);
        }

        function cerrarLugares() {
            const modal = document.querySelector('.modal');
            if (modal) {
                document.body.removeChild(modal); // Elimina el modal
            }
        }

        function crearModal(contenido) {
            const modal = document.createElement('div');
            modal.className = 'modal';
            modal.innerHTML = contenido;
            document.body.appendChild(modal);
        }

        function mostrarFormulario(tipo) {
            const modal = document.createElement('div');
            modal.className = 'modal';
            modal.innerHTML = `
                <div class="modal-content">
                    <h2>${tipo === 'login' ? 'Iniciar Sesión' : 'Registrarse'}</h2>
                    <form>
                        <label for="${tipo === 'login' ? 'username' : 'newUsername'}">Usuario:</label>
                        <input type="text" id="${tipo === 'login' ? 'username' : 'newUsername'}" name="${tipo === 'login' ? 'username' : 'newUsername'}" required>
                        <label for="${tipo === 'login' ? 'password' : 'newPassword'}">Contraseña:</label>
                        <input type="password" id="${tipo === 'login' ? 'password' : 'newPassword'}" name="${tipo === 'login' ? 'password' : 'newPassword'}" required>
                        <button type="submit">${tipo === 'login' ? 'Entrar' : 'Registrar'}</button>
                        <button type="button" class="close-btn" onclick="cerrarFormulario()">Cerrar</button>
                    </form>
                </div>
            `;
            document.body.appendChild(modal);
        }

        function cerrarFormulario() {
            const modal = document.querySelector('.modal');
            if (modal) {
                document.body.removeChild(modal); // Elimina el modal
            }
        }
    </script>
</head>
<body>

    <header>
        <img src="./Diseño sin título.png" alt="Logo de Colombia Expediciones" class="logo">
        <h1 class="titulo">Colombia Expediciones</h1>
        <nav>
            <ul>
                <li><a href="#" onclick="resetPage()">Regresar</a></li>  
                <li><a href="#" onclick="mostrarLugares()">Conoce</a></li>
                <li><a href="#" onclick="mostrarFormulario('login')">Inicia sesión</a></li>
                <li><a href="#" onclick="mostrarFormulario('register')">Regístrate</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section>
            <article>
                <h2>🌍 ¡Descubre lo mejor de Santander con Colombia Expediciones! 🌍</h2>
                <p>🏞️ Ubicados en San Gil, el corazón de la aventura en Colombia, somos tu mejor opción para vivir experiencias inolvidables rodeadas de naturaleza, emoción y cultura.</p>
                <h3>🚵‍♂️ ¿Listo para la aventura? Ofrecemos:</h3>
                <ul>
                    <li>
                        ✨ Rafting en el Río Fonce
                        <img src="./raft.jpg" alt="Rafting en el Río Fonce" class="actividad-imagen">
                    </li>
                    <li>
                        ✨ Parapente en el Cañón del Chicamocha
                        <img src="./parapente.jpg" alt="Parapente en el Cañón del Chicamocha" class="actividad-imagen">
                    </li>
                    <li>
                        ✨ Ciclismo de montaña por senderos espectaculares
                        <img src="./ciclismo.jpg" alt="Ciclismo de montaña" class="actividad-imagen">
                    </li>
                    <li>
                        ✨ Caminatas ecológicas
                        <img src="./caminata.jpg" alt="Caminatas ecológicas" class="actividad-imagen">
                    </li>
                    <li>
                        ✨ Tours por pueblos coloniales (Barichara, Guane y más)
                        <img src="./tours.jpg" alt="Tours por pueblos coloniales" class="actividad-imagen">
                    </li>
                    <li>
                        ✨ Escalada y rappel en cascadas
                        <img src="./escalada.jpg" alt="Escalada y rappel en cascadas" class="actividad-imagen">
                    </li>
                </ul>
                <p>🎒 ¡Desde excursiones familiares hasta desafíos extremos, tenemos el plan perfecto para ti!</p>
                <p>📅 Planifica tu próxima escapada con nosotros. Tenemos paquetes adaptados a tus gustos y presupuesto. ¡Déjanos ser tu guía hacia la aventura!</p>
                <p>📲 Contáctanos ahora y asegura tu cupo para una experiencia que nunca olvidarás.</p>
                <p>👍 Síguenos en nuestra cuenta oficial en Facebook como <a href="https://www.facebook.com/profile.php?id=61565986292890" target="_blank" rel="noopener noreferrer">Colombia Expediciones</a> y en Instagram como <a href="https://www.instagram.com/colombiaexpedicionescol" target="_blank" rel="noopener noreferrer">colombiaexpedicionescol</a>. Comparte tu historia de aventura usando #ColombiaExpediciones</p>
                <button onclick="window.location.href='https://www.facebook.com/profile.php?id=61565986292890'">Consulta hoy</button>
            </article>
        </section>
    </main>

    <footer>
        <p>&copy; 2024 Colombia Expediciones. Todos los derechos reservados.</p>
    </footer>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    margin: 0;
    padding: 0;
    background-color: #f4f4f4;
}

header {
    background-color: #0033A0; /* Color de fondo azul */
    color: white;
    padding: 20px 0;
    text-align: center;
}

.logo {
    width: 150px; /* Ajusta el tamaño del logo según sea necesario */
    margin-bottom: 10px;
}

.titulo {
    font-size: 3em; /* Tamaño de fuente más grande */
    margin: 0;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin: 0 15px;
}

nav a {
    color: white;
    text-decoration: none;
}

main {
    padding: 20px;
    max-width: 800px;
    margin: auto;
    background: white;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

h1, h2, h3 {
    color: #333;
}

ul {
    padding-left: 20px;
}

button {
    background: #007bff;
    color: white;
    border: none;
    padding: 10px 15px;
    cursor: pointer;
    margin-top: 20px;
}

button:hover {
    background: #0056b3;
}

.actividad-imagen {
    width: 100%; /* Ajusta el tamaño según sea necesario */
    max-width: 400px; /* Tamaño máximo de las imágenes */
    margin: 10px auto; /* Centrar las imágenes */
    display: block; /* Para asegurarnos de que se comporten como bloques */
    border-radius: 8px; /* Bordes redondeados */
    box-shadow: 0 0 5px rgba(0, 0, 0, 0.2); /* Sombra suave */
}

footer {
    text-align: center;
    padding: 10px 0;
    background: #007bff;
    color: white;
    position: relative;
    bottom: 0;
    width: 100%;
}
