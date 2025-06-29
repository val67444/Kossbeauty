
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  
  <style>
    :root {
      --color-fondo-claro: #f5eafd;
      --color-texto-claro: #7435a5;
      --color-fondo-oscuro: #2a1a3f;
      --color-texto-oscuro: #d6b0ff;
      --color-boton-wsp: #d6b0ff;
      --color-boton-wsp-oscuro: #8a6acb;
      --color-producto-fondo-claro: #fff0ff;
      --color-producto-fondo-oscuro: #4b3a65;
      --color-boton-producto-claro: #c58cff;
      --color-boton-producto-oscuro: #a071d2;
      --color-borde-buscador-claro: #a05fc7;
      --color-borde-buscador-oscuro: #bda1e9;
    }
    /* Transiciones para modo claro/oscuro */
    body, header, .producto, #carrito, footer, input, #carrito-icono, .boton-wsp, button {
      transition: background-color 0.4s ease, color 0.4s ease, border-color 0.4s ease;
    }
    /* Modo claro (default) */
    body {
      background-color: var(--color-fondo-claro);
      font-family: 'Segoe UI', sans-serif;
      color: var(--color-texto-claro);
      margin: 0;
      padding: 0;
    }
    header {
      text-align: center;
      padding: 40px 20px 10px;
    }
    h1 {
      font-size: 3em;
      margin: 0;
    }
    .moñito {
      font-size: 2.5em;
    }
    .boton-wsp {
      background-color: var(--color-boton-wsp);
      color: white;
      padding: 12px 25px;
      border: none;
      border-radius: 20px;
      font-size: 1em;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      margin-top: 10px;
      user-select: none;
    }
    #buscador {
      margin: 30px auto 10px;
      padding: 10px;
      font-size: 1em;
      border: 2px solid var(--color-borde-buscador-claro);
      border-radius: 10px;
      width: 80%;
      max-width: 400px;
      display: block;
      color: var(--color-texto-claro);
      background-color: white;
    }
    lista.forEach((producto, index) => {
  const prodDiv = document.createElement('div');
  prodDiv.classList.add('producto');
  prodDiv.style.animationDelay = `${index * 0.1}s`; // 💡 NUEVO
  prodDiv.innerHTML = `
    <img src="${producto.imagen}" alt="${producto.nombre}" />
    <h3>${producto.nombre}</h3>
    <p>${producto.descripcion}</p>
    <strong>Gs. ${producto.precio.toLocaleString()}</strong>
    <button onclick="agregarAlCarrito(${index})">Agregar al carrito</button>
  `;
  catalogo.appendChild(prodDiv);
});

.catalogo {
  max-width: 1200px;
  margin: 0 auto;
  width: 100%;
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 30px;
  padding: 20px;
  box-sizing: border-box;
}

.producto {
  background: var(--color-producto-fondo-claro, white);
  border-radius: 15px;
  box-shadow: 0 2px 6px rgba(0,0,0,0.15);
  padding: 20px;
  width: 250px;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.producto img {
  width: 100%;
  height: auto;
  border-radius: 10px;
  margin-bottom: 12px;
}

.producto h3 {
  margin: 10px 0;
  color: #8a3dbb;
}

.producto p {
  font-size: 0.95em;
}

.producto strong {
  font-size: 1.2em;
  color: #5b2b82;
}

.producto button {
  margin-top: auto;
  padding: 8px 16px;
  background-color: var(--color-boton-producto-claro, #a05fc7);
  color: white;
  border: none;
  border-radius: 15px;
  cursor: pointer;
  user-select: none;
  transition: background-color 0.3s ease;
}

.producto button:hover {
  background-color: #7a3e99;
}

    #carrito-icono {
      position: fixed;
      top: 20px;
      right: 20px;
      font-size: 1.3em;
      background-color: var(--color-boton-producto-claro);
      color: white;
      padding: 10px 20px;
      border-radius: 30px;
      cursor: pointer;
      user-select: none;
      display: flex;
      align-items: center;
      gap: 8px;
      z-index: 1100;
    }
    #carrito {
      position: fixed;
      top: 70px;
      right: 20px;
      background: white;
      color: var(--color-texto-claro);
      border: 2px solid var(--color-boton-producto-claro);
      border-radius: 15px;
      padding: 20px;
      display: none;
      width: 280px;
      z-index: 1000;
      box-shadow: 0 4px 10px rgba(116, 53, 165, 0.5);
    }
    #carrito h4 {
      margin-top: 0;
      color: var(--color-texto-claro);
    }
    #carrito ul {
      list-style: none;
      padding-left: 0;
      max-height: 200px;
      overflow-y: auto;
      margin-bottom: 10px;
      color: var(--color-texto-claro);
    }
    #carrito ul li {
      margin-bottom: 6px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 0.95em;
    }
    #carrito ul li button {
      background-color: transparent;
      border: none;
      color: var(--color-boton-producto-claro);
      cursor: pointer;
      font-weight: bold;
      font-size: 1em;
      user-select: none;
      padding: 0 4px;
      border-radius: 6px;
      transition: background-color 0.3s ease;
    }
    #carrito ul li button:hover {
      background-color: var(--color-boton-producto-claro);
      color: white;
    }
    #carrito p strong {
      font-size: 1.1em;
      color: var(--color-texto-claro);
    }
    #carrito .boton-wsp {
      display: block;
      margin: 10px auto 0;
      width: 90%;
      text-align: center;
    }
    .mensaje {
      background-color: #e6d0ff;
      padding: 10px;
      border-radius: 10px;
      margin: 10px auto;
      text-align: center;
      display: none;
      width: 90%;
      max-width: 400px;
      color: var(--color-texto-claro);
      user-select: none;
    }
    .seccion-comprar {
      padding: 30px;
      text-align: center;
    }
    footer {
      background-color: #eed9ff;
      text-align: center;
      padding: 20px;
      margin-top: 40px;
      color: var(--color-texto-claro);
    }
    footer a {
      color: var(--color-texto-claro);
      text-decoration: none;
      margin: 0 10px;
      font-weight: bold;
      user-select: none;
    }
    .nosotras-link {
      display: inline-block;
      margin-top: 10px;
      font-size: 1.1em;
      color: var(--color-texto-claro);
      text-decoration: underline;
      font-weight: bold;
      user-select: none;
    }
    /* Botón modo oscuro */
    #btn-modo {
      position: fixed;
      top: 20px;
      left: 20px;
      background: transparent;
      border: none;
      font-size: 1.7em;
      cursor: pointer;
      user-select: none;
      color: var(--color-texto-claro);
      transition: color 0.4s ease;
      z-index: 1100;
    }
    /* Modo oscuro */
    body.dark {
      background-color: var(--color-fondo-oscuro);
      color: var(--color-texto-oscuro);
    }
    body.dark header {
      color: var(--color-texto-oscuro);
    }
    body.dark #buscador {
      background-color: #3e2f5b;
      border-color: var(--color-borde-buscador-oscuro);
      color: var(--color-texto-oscuro);
    }
    body.dark .boton-wsp {
      background-color: var(--color-boton-wsp-oscuro);
    }
    body.dark .producto {
      background: var(--color-producto-fondo-oscuro);
      box-shadow: 0 0 12px rgba(186, 150, 255, 0.7);
    }
    body.dark .producto h3 {
      color: #c9b4ff;
    }
    body.dark .producto strong {
      color: #c9b4ff;
    }
    body.dark .producto button {
      background-color: var(--color-boton-producto-oscuro);
    }
    body.dark #carrito {
      background: #3e2f5b;
      color: var(--color-texto-oscuro);
      border-color: var(--color-boton-producto-oscuro);
      box-shadow: 0 4px 10px rgba(186, 150, 255, 0.7);
    }
    body.dark #carrito h4,
    body.dark #carrito ul,
    body.dark #carrito p strong,
    body.dark #carrito ul li,
    body.dark footer,
    body.dark footer a,
    body.dark .nosotras-link {
      color: var(--color-texto-oscuro);
    }
    body.dark #carrito ul li button {
      color: var(--color-boton-producto-oscuro);
    }
    body.dark #carrito ul li button:hover {
      background-color: var(--color-boton-producto-oscuro);
      color: white;
    }
    body.dark #carrito .boton-wsp {
      background-color: var(--color-boton-producto-oscuro);
    }
    body.dark #carrito-icono {
      background-color: var(--color-boton-producto-oscuro);
    }
    body.dark #btn-modo {
      color: var(--color-texto-oscuro);
    }
    .decoracion {
  position: fixed;
  pointer-events: none;
  user-select: none;
  animation: flotar 15s ease-in-out infinite;
}

@keyframes flotar {
  0% {
    transform: translateY(0) rotate(0deg);
  }
  50% {
    transform: translateY(-20px) rotate(180deg);
  }
  100% {
    transform: translateY(0) rotate(360deg);
  }
}

    /* 🌸 Animación de productos */
.producto {
  opacity: 0;
  transform: translateY(20px);
  animation: aparecer 0.8s ease forwards;
}

@keyframes aparecer {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 💓 Título con latido */
h1 {
  animation: latido 3s ease-in-out infinite;
}

@keyframes latido {
  0%, 100% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.03);
  }
}

/* ✨ Fondo animado claro y oscuro */
body {
  background: linear-gradient(270deg, #f5eafd, #fce4ff, #f5eafd);
  background-size: 600% 600%;
  animation: fondoMovil 60s ease infinite;
}

body.dark {
  background: linear-gradient(270deg, #2a1a3f, #3b2b5a, #2a1a3f);
}

/* Animación del fondo */
@keyframes fondoMovil {
  0% { background-position: 0% 50%; }
  50% { background-position: 100% 50%; }
  100% { background-position: 0% 50%; }
}

/* 🌙 Giro al cambiar de modo */
#btn-modo {
  transition: transform 0.4s ease;
}
#btn-modo.rotar {
  transform: rotate(360deg);
}

                                    .seccion-delivery {
  background-color: #fceaff;
  border-radius: 15px;
  margin: 20px auto;
  max-width: 600px;
  box-shadow: 0 0 10px rgba(116, 53, 165, 0.2);
}
body.dark .seccion-delivery {
  background-color: #3b2b5a;
  color: var(--color-texto-oscuro);
  box-shadow: 0 0 10px rgba(186, 150, 255, 0.4);
}
<head>
  <style>
    /* 👇 Pon esto dentro del style */
    .mensaje {
      position: fixed;
      bottom: 20px;
      left: 50%;
      transform: translateX(-50%);
      background-color: #28a745;
      color: white;
      padding: 10px 20px;
      border-radius: 5px;
      display: none;
      z-index: 1000;
    }

    #pantalla-bienvenida {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #f5eafd;
  color: #7435a5;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  font-size: 1.8em;
  text-align: center;
  padding: 20px;
  animation: fadeOut 1s ease forwards;
  animation-delay: 3s; /* Duración antes de desaparecer */
  pointer-events: none;
}

@keyframes fadeOut {
  to {
    opacity: 0;
    visibility: hidden;
  }
}

#pantalla-bienvenida {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: #f5eafd;
  color: #7435a5;
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 9999;
  font-size: 1.5em;
  text-align: center;
  padding: 20px;
  animation: fadeOut 1s ease forwards;
  animation-delay: 1.2s;
  pointer-events: none;
}

#pantalla-bienvenida img {
  width: 279px; /* o 300px si querés más grande */
  margin-bottom: 20px;
}

.contenido-bienvenida {
  display: flex;
  flex-direction: column;
  align-items: center;
}

@keyframes fadeOut {
  to {
    opacity: 0;
    visibility: hidden;
  }
}
                                    
  </style>
</head>
<body>
<div id="pantalla-bienvenida">
  <div class="contenido-bienvenida">
    <img src="https://i.postimg.cc/RCnnNC2y/Whats-App-Image-2025-06-15-at-12-18-22.jpg" alt="Logo de la marca" />
    <h2> </h2>
  </div>
</div>


<div id="mensaje-agregado" class="mensaje">
  ¡Producto agregado con amor! 💕
</div>
  <!-- Botón modo oscuro -->
  <button id="btn-modo" aria-label="Cambiar modo oscuro">🌙</button>

  <div id="carrito-icono" onclick="mostrarCarrito()" title="Mostrar carrito">
    🛒 <span id="contador">0</span>
  </div>

  <header>
    <div class="moñito">🎀</div>
    <h1>Bienvenida Hermosa!</h1>
    <p>A tu rincón de magia, ternura y elegancia 💜🌸🌙</p>
    <a href="https://wa.me/595992982248" class="boton-wsp" target="_blank" rel="noopener noreferrer">Hacé tu pedido por WhatsApp</a>
  </header>

  <input type="text" id="buscador" placeholder="Buscar producto...🌷" aria-label="Qué producto estás buscando hoy, hermosa? 🌸" />

  <div id="mensaje" class="mensaje" role="alert" aria-live="polite">¡Producto agregado con amor! 💕</div>

  <div class="catalogo" id="catalogo">
    <!-- Productos se cargarán aquí -->
  </div>

  <div id="carrito" aria-live="polite" aria-label="Carrito de compras">
    <h4>Tu carrito 🛍️</h4>
    <ul id="lista-carrito"></ul>
    <p><strong>Total: Gs. <span id="total">0</span></strong></p>
    <a id="finalizar" href="#" target="_blank" rel="noopener noreferrer" class="boton-wsp">Finalizar en WhatsApp</a>
    <button onclick="vaciarCarrito()" style="margin-top:10px; background:#a05fc7; border:none; color:white; padding:8px 16px; border-radius:15px; cursor:pointer; user-select:none;">Vaciar carrito</button>
  </div>

  <div class="seccion-comprar">
    <h2>¿Cómo comprar?</h2>
    <p>1. Elegí tus productos 💕</p>
    <p>2. Agregalos al carrito 🛍️</p>
    <p>3. Finalizá en WhatsApp ✨</p>
    <p>4. Coordinamos entrega/envío 📦</p>
  </div>
 
   <div class="seccion-delivery" style="text-align: center; padding: 20px;">
  <h2>Envíos y Entregas 🚚</h2>
  <p>📍 Envíos disponibles en todo Asunción, Fernando zona sur y San lorenzo </p>
  <p>🕐 Coordinamos horarios flexibles.</p>
  <p>💰 Costo de delivery varía según zona .</p>
  <p>💜 También podés retirar en zona <strong>Fernando zona sur </strong>.</p>
</div>

<div class="seccion-pago" style="text-align:center; padding: 30px;">
  <h2>Medios de pago 💰</h2>
  <p><strong>✔🌸 Efectivo</strong>: al recibir el producto o acordar entrega.</p>
  <p><strong>✔🌸 Transferencias bancarias</strong></p>
  <footer>
  <p>Seguinos en redes ✨</p>
  <a href="https://www.instagram.com/koss___beauty" target="_blank" rel="noopener noreferrer">Instagram</a> |
  <a href="https://tiktok.com/@kossbeauty" target="_blank" rel="noopener noreferrer">TikTok</a><br /><br />

  <p style="max-width: 500px; margin: auto; font-size: 0.95em; line-height: 1.5;">
   <h2>Mi Historia 💜</h2>

Kossbeauty nació el 10 de septiembre del 2024, como un sueño personal lleno de ilusión. Desde siempre soñé con tener mi propia tienda, y aunque empecé sola, puse todo mi corazón, esfuerzo y dedicación en cada detalle.🌸

Gracias a cada una de ustedes que confía en mí, estoy más cerca de cumplir ese gran sueño: abrir mi tienda física. Cada compra, cada mensaje y cada gesto me llena el alma.
¡Gracias por ser parte de esto! ✨🌷

Quiero hacer un agradecimiento especial a mi mamá y mi hermano, que siempre estuvieron a mi lado en cada paso, apoyándome, animándome y creyendo en mí, incluso cuando yo dudaba.
Sin ustedes, esto no sería posible. Los amo. 💖
  </p>
</footer>

  <script>
    // Productos (puedes añadir más fácilmente aquí)
    const productosData = [ 
  {
    nombre: "Corrector D`hermosa ",
    descripcion: "Cobertura precisa y práctica! Nuestro corrector en formato giratorio con aplicador en pincel ofrece una aplicación suave y uniforme.",
    precio: 14500,
    imagen: "https://i.postimg.cc/rF6w3yyg/corrector.jpg"
  },
  {
    nombre: "Iluminador mágico 🌙",
    descripcion: "Místico y con olor a empoderamiento ✨",
    precio: 12500,
    imagen: "https://i.postimg.cc/y8c9trz3/iluminador-2.jpg"
  },
  {
    nombre: "Kit iluminador y broncer 🦋",
    descripcion: "Set para brillar y florecer como vos 🌸",
    precio: 12500,
    imagen: "https://i.postimg.cc/SR4NXVv3/iluminador.jpg"
  },
  {
    nombre: "Jelly Tint",
    descripcion: "Enamórate de esta innovadora tinta para labios y mejillas de larga duración. ¡Un toque y sos arte! ✨",
    precio: 13500,
    imagen: "https://i.postimg.cc/HkMYtq1R/Whats-App-Image-2025-06-13-at-11-32-30-2.jpg"
  },
  {
    nombre: "Lip Tint",
    descripcion: "Cuida tus labios con brillo cósmico de alta duración ✨",
    precio: 12000,
    imagen: "https://i.postimg.cc/pTPhn24P/Whats-App-Image-2025-06-13-at-11-32-30-4.jpg"
  },
  {
    nombre: "Hebilla de Flor 🌸",
    descripcion: "Accesorio tierno y delicado para darle un toque mágico a tu peinado. ¡La flor que te acompaña con estilo!",
    precio: 7000,
    imagen: "https://i.postimg.cc/c4JxjFV1/Whats-App-Image-2025-06-13-at-13-54-24.jpg"
  },
  {
    nombre: "Arqueador de Pestañas ✨",
    descripcion: "Realzá tu mirada con nuestro arqueador: práctico, elegante y suave. ¡Mirada encantadora asegurada!",
    precio: 14500,
    imagen: "https://i.postimg.cc/vH5J0fm8/Whats-App-Image-2025-06-13-at-13-54-47.jpg"
  },
  {
    nombre: "Mascarilla Facial 🍃",
    descripcion: "Cuida tu piel con frescura y amor. Mascarillas nutritivas que limpian, hidratan y renuevan tu rostro. ¡Ritual de belleza en minutos!",
    precio: 1000,
    imagen: "https://i.postimg.cc/Y2WZSYYN/Whats-App-Image-2025-06-13-at-13-57-04.jpg"
  },
  {
    nombre: "Labial de Frutilla 🍓",
    descripcion: "Dulce color y aroma irresistible. Este labial cremoso con esencia frutal es ideal para labios suaves y con vida.",
    precio: 11500,
    imagen: "https://i.postimg.cc/4dhLmR74/Whats-App-Image-2025-06-13-at-13-57-04-1.jpg"
  },
// ... Otros productos
{
  nombre: "Mascara de Pestañas Volumen Total SkyHigh",
  descripcion: "Para tener pestañas largas y voluminosas, como siempre soñaste.",
  precio: 15000,
  imagen: " https://i.postimg.cc/RC1q9BLc/Whats-App-Image-2025-06-14-at-07-09-38.jpg"
},
// ... Otros productos
{
  nombre: "Kitti kiss🐈‍",
  descripcion: "Hidrata, cuida y resalta tu belleza natural.",
  precio: 15000,
  imagen: "https://i.postimg.cc/sDqcXwRd/Whats-App-Image-2025-06-20-at-06-44-26.jpg"
},
// ... Otros productos
{
  nombre: "Lip oil ✨",
  descripcion: "Nutre, repara brillo natural que cambia con el pH de tus labios.",
  precio: 11500,
  imagen: "https://i.postimg.cc/pTM8b68k/Whats-App-Image-2025-06-20-at-06-44-25.jpg"
},
// Nuevos productos
{
  nombre: "What A Tint!💎",
  descripcion: "Son un producto 2 en 1, no pegajoso y con una consistencia similar al agua.",
  precio: 11500,
  imagen: "https://i.postimg.cc/NMLnSbhN/Whats-App-Image-2025-06-20-at-06-44-26-1.jpg"
},
{
  nombre: "Mascarilla para labios✨",
  descripcion: "Besitos suaves, labios renovados. Mientras dormís, ella hace su magia.",
  precio: 4000,
  imagen: "https://i.postimg.cc/sgMdtVpP/Whats-App-Image-2025-06-20-at-07-34-29.jpg"
},
{
  nombre: "Mascarillas faciales frutales🍏",
  descripcion: "Despertá tu piel con un shot de energía. Textura ligera y perfume cítrico.",
  precio: 5500,
  imagen: "https://i.postimg.cc/P5sQkyD6/Whats-App-Image-2025-06-20-at-07-34-29-1.jpg"
}
];
    
   // Variables DOM
    const catalogo = document.getElementById('catalogo');
    const carritoIcono = document.getElementById('carrito-icono');
    const carritoContador = document.getElementById('contador');
    const carritoDiv = document.getElementById('carrito');
    const listaCarrito = document.getElementById('lista-carrito');
    const totalSpan = document.getElementById('total');
    const mensaje = document.getElementById('mensaje');
    const btnModo = document.getElementById('btn-modo');
    const buscador = document.getElementById('buscador');
    const finalizarLink = document.getElementById('finalizar');

    let carrito = [];

    // Cargar productos dinámicamente
    function cargarProductos(lista) {
      catalogo.innerHTML = '';
      lista.forEach((producto, index) => {
        const prodDiv = document.createElement('div');
        prodDiv.classList.add('producto');
        prodDiv.innerHTML = `
          <img src="${producto.imagen}" alt="${producto.nombre}" />
          <h3>${producto.nombre}</h3>
          <p>${producto.descripcion}</p>
          <strong>Gs. ${producto.precio.toLocaleString()}</strong>
          <button onclick="agregarAlCarrito(${index})">Agregar al carrito</button>
        `;
        catalogo.appendChild(prodDiv);
      });
      
    }  

    // Agregar producto al carrito
    function agregarAlCarrito(indice) {
      const producto = productosData[indice];
      carrito.push(producto);
      actualizarCarrito();
      mostrarMensaje();
    }

    // Actualizar carrito
    function actualizarCarrito() {
      listaCarrito.innerHTML = '';
      let total = 0;
      carrito.forEach((producto, index) => {
        total += producto.precio;
        const li = document.createElement('li');
        li.innerHTML = `${producto.nombre} - Gs. ${producto.precio.toLocaleString()} <button aria-label="Quitar ${producto.nombre}" onclick="quitarDelCarrito(${index})">x</button>`;
        listaCarrito.appendChild(li);
      });
      totalSpan.textContent = total.toLocaleString();
      carritoContador.textContent = carrito.length;
      actualizarFinalizarLink();
    }

    // Quitar producto del carrito
    function quitarDelCarrito(indice) {
      carrito.splice(indice, 1);
      actualizarCarrito();
    }

    // Vaciar carrito
    function vaciarCarrito() {
      carrito = [];
      actualizarCarrito();
    }

    // Mostrar/Ocultar carrito
    function mostrarCarrito() {
      if(carritoDiv.style.display === 'block'){
        carritoDiv.style.display = 'none';
      } else {
        carritoDiv.style.display = 'block';
      }
    }

    // Mostrar mensaje breve
    function mostrarMensaje() {
      mensaje.style.display = 'block';
      setTimeout(() => {
        mensaje.style.display = 'none';
      }, 2000);
    }

    // Filtrar productos con buscador
    buscador.addEventListener('input', () => {
      const texto = buscador.value.toLowerCase();
      const filtrados = productosData.filter(p => 
        p.nombre.toLowerCase().includes(texto) ||
        p.descripcion.toLowerCase().includes(texto)
      );
      cargarProductos(filtrados);
    });

    // Actualizar link para finalizar compra en WhatsApp
    function actualizarFinalizarLink() {
      if(carrito.length === 0){
        finalizarLink.href = '#';
        finalizarLink.style.pointerEvents = 'none';
        finalizarLink.style.opacity = '0.6';
        return;
      }
      let mensajeWsp = 'Hola! Quiero hacer un pedido:%0A';
      carrito.forEach(producto => {
        mensajeWsp += `- ${producto.nombre} (Gs. ${producto.precio.toLocaleString()})%0A`;
      });
      let total = carrito.reduce((acc, p) => acc + p.precio, 0);
      mensajeWsp += `%0ATotal: Gs. ${total.toLocaleString()}`;
      finalizarLink.href = `https://wa.me/595992982248?text=${mensajeWsp}`;
      finalizarLink.style.pointerEvents = 'auto';
      finalizarLink.style.opacity = '1';
    }

    // FUNCIONES PARA DECORACIONES

function crearDecoraciones(tipo) {
  // Elimina decoraciones anteriores
  document.querySelectorAll('.decoracion').forEach(e => e.remove());

  const cantidad = 49;
  for (let i = 0; i < cantidad; i++) {
    const deco = document.createElement('div');
    deco.classList.add('decoracion');
    deco.textContent = tipo === 'estrella' ? '✨' : '🌸';

    // Estilos más suaves
    const size = Math.random() * 1 + 0.6; // más pequeñas
    deco.style.fontSize = `${size}em`;
    deco.style.position = 'fixed';
    deco.style.top = `${Math.random() * 100}vh`;
    deco.style.left = `${Math.random() * 100}vw`;
    deco.style.pointerEvents = 'none';
    deco.style.opacity = '0.25'; // MUCHO más sutil
    deco.style.zIndex = '-1'; // más al fondo
    deco.style.userSelect = 'none';
    deco.style.filter = 'blur(0.5px)';
    deco.style.animation = 'flotar 15s ease-in-out infinite';
    deco.style.transform = `rotate(${Math.random() * 360}deg)`;

    document.body.appendChild(deco);
  }

}

// BOTÓN DE MODO OSCURO

btnModo.addEventListener('click', () => {
  document.body.classList.toggle('dark');
  
  // ✨ Giro de botón
  btnModo.classList.add('rotar');
  setTimeout(() => btnModo.classList.remove('rotar'), 400);
  
  if (document.body.classList.contains('dark')) {
    btnModo.textContent = '☀️';
    btnModo.setAttribute('aria-label', 'Cambiar a modo claro');
    localStorage.setItem('modo', 'oscuro');
    crearDecoraciones('estrella');
  } else {
    btnModo.textContent = '🌙';
    btnModo.setAttribute('aria-label', 'Cambiar a modo oscuro');
    localStorage.setItem('modo', 'claro');
    crearDecoraciones('mariposa');
  }
});


// CARGAR MODO GUARDADO + DECORACIONES

function cargarModo() {
  const modo = localStorage.getItem('modo') || 'claro';
  if (modo === 'oscuro') {
    document.body.classList.add('dark');
    btnModo.textContent = '☀️';
    btnModo.setAttribute('aria-label', 'Cambiar a modo claro');
    crearDecoraciones('estrella');
  } else {
    document.body.classList.remove('dark');
    btnModo.textContent = '🌙';
    btnModo.setAttribute('aria-label', 'Cambiar a modo oscuro');
    crearDecoraciones('mariposa');
  }
}

// INICIALIZACIONES
cargarProductos(productosData);
actualizarCarrito();
cargarModo();
</script>
