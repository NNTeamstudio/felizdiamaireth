
const express = require('express');
const colorNamer = require('color-namer');

// Inicializar la aplicación
const app = express();

// Definir el puerto en el que el servidor escuchará


// Mapa de traducción de nombres de colores al español
const colorTranslations = {
    "red": "Rojo",
    "green": "Verde",
    "blue": "Azul",
    "black": "Negro",
    "white": "Blanco",
    "yellow": "Amarillo",
    "orange": "Naranja",
    "pink": "Rosa",
    "purple": "Púrpura",
    "brown": "Marrón",
    "gray": "Gris",
    "cyan": "Cian",
    "magenta": "Magenta",
    "violet": "Violeta",
    "turquoise": "Turquesa",
    "indigo": "indigo",
    "gold": "Oro",
    "silver": "Plata",
    "bronze": "Bronce",
    "teal": "Celeste",
    "lime": "Lima",
    
    // Agrega más traducciones según sea necesario
};

// Crear el endpoint para la raíz
app.get('/', (req, res) => {
    res.send(
    "Welcome to the Colors API. Get: /colors");
});

// Crear el endpoint para manejar la conversión de color
app.get('/colors', (req, res) => {
    // Obtener el valor hexadecimal del color desde los parámetros de la consulta
    const hex = req.query.hex;

    // Validar que se proporcione un código hexadecimal válido
    if (!/^#?[0-9A-F]{6}$/i.test(hex)) {
        return res.status(400).json({
            error: "Codigo hexadecimal invalido"});
    }

    // Convertir el código hexadecimal al nombre del color
    const namedColors = colorNamer(hex);
    const colorNameInEnglish = namedColors.basic[0].name;

    // Traducir el nombre del color al español
    const colorNameInSpanish = colorTranslations[colorNameInEnglish.toLowerCase()] || colorNameInEnglish;

    // Devolver el nombre del color como respuesta
    res.json({
      color:  `${colorNameInSpanish}`});
});


