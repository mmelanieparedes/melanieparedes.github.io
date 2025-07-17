<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<title>Gourmet Elegante</title>
<meta name="viewport" content="width=device-width,initial-scale=1" />
<style>
  @import url('https://fonts.googleapis.com/css2?family=Montserrat&family=Playfair+Display&display=swap');

  :root {
    --bg-light: #F2E6D6;      
    --bg-dark: #4B3C32;       
    --accent: #C29A6D;        
    --text-dark: #3A2C27;     
    --btn-hover: #A65E2E;     
  }

  body {
    margin: 0;
    font-family: 'Montserrat', sans-serif;
    background: var(--bg-light);
    color: var(--text-dark);
  }

  header {
    background: var(--bg-dark);
    color: var(--bg-light);
    padding: 1rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  header h1 {
    font-family: 'Playfair Display', serif;
    margin: 0;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  header h1 img {
    width: 40px;
    height: 40px;
    border-radius: 5px;
    object-fit: contain;
  }

  nav a,
  nav button {
    color: var(--bg-light);
    margin: 0 0.5rem;
    text-decoration: none;
    background: none;
    border: none;
    cursor: pointer;
    font-size: 1rem;
    padding: 0.3rem;
    transition: border-color 0.3s;
  }

  nav a.active,
  nav button.active {
    border-bottom: 2px solid var(--accent);
  }

  .container {
    padding: 2rem;
  }

  .tabs {
    display: none;
  }

  .tabs.active {
    display: block;
  }

  /* ----------- Inicio: centrado ----------- */
  #inicio {
    text-align: center;
  }

  #inicio p {
    font-size: 1.1rem;
    line-height: 1.5;
    max-width: 600px;
    margin: 0 auto 1.5rem;
  }

  #inicio img {
    max-width: 90vw;
    max-height: 320px;
    object-fit: cover;
    border-radius: 12px;
    box-shadow: 0 6px 14px rgba(0,0,0,0.2);
  }
  /* ----------- Fin inicio centrado ----------- */

  .filter-btn {
    background: var(--accent);
    color: var(--bg-dark);
    border: none;
    padding: 0.5rem 1rem;
    margin: 0.25rem;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .filter-btn:hover,
  .filter-btn.active {
    background: var(--btn-hover);
    color: var(--bg-light);
  }

  .menu-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
    gap: 1.5rem;
    margin-top: 1rem;
  }

  .menu-item {
    background: #fff;
    padding: 1rem;
    border-radius: 8px;
    box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    text-align: center;
    transition: transform 0.3s ease;
  }
  .menu-item:hover {
    transform: translateY(-5px);
  }

  .menu-item img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 8px;
  }

  .menu-footer {
    margin-top: 0.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .btn {
    background: var(--accent);
    color: var(--bg-dark);
    border: none;
    padding: 0.5rem 1rem;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .btn:hover {
    background: var(--btn-hover);
    color: var(--bg-light);
  }

  #carrito {
    position: fixed;
    top: 0;
    right: -350px;
    width: 320px;
    height: 100%;
    background: #fff;
    box-shadow: -2px 0 8px rgba(0, 0, 0, 0.2);
    transition: right 0.3s;
    padding: 1rem;
    display: flex;
    flex-direction: column;
    z-index: 999;
    border-left: 4px solid var(--accent);
  }

  #carrito.open {
    right: 0;
  }

  #carrito h2 {
    margin-top: 0;
    font-family: 'Playfair Display', serif;
    color: var(--bg-dark);
  }

  .cart-items {
    flex: 1;
    overflow-y: auto;
    margin: 0.5rem 0;
  }

  .cart-item {
    display: flex;
    justify-content: space-between;
    margin: 0.5rem 0;
    font-weight: 600;
  }

  footer {
    text-align: center;
    padding: 1.5rem;
    background: var(--bg-dark);
    color: var(--bg-light);
    margin-top: 2rem;
    font-size: 0.9rem;
    position: relative;
  }

  .socials {
    margin-top: 1rem;
  }

  .socials a {
    margin: 0 0.5rem;
    color: var(--accent);
    font-size: 1.5rem;
    text-decoration: none;
    transition: color 0.3s;
  }

  .socials a:hover {
    color: var(--btn-hover);
  }

  /* ----------- Formulario Contacto centrado ----------- */
  #contacto form {
    max-width: 400px;
    margin: 0 auto;
    text-align: center;
  }

  #contacto label {
    display: block;
    margin-bottom: 1rem;
    font-weight: 600;
  }

  #contacto input[type="text"],
  #contacto input[type="email"],
  #contacto textarea {
    width: 100%;
    padding: 0.5rem;
    border-radius: 6px;
    border: 1px solid #ccc;
    font-size: 1rem;
  }

  #contacto textarea {
    resize: vertical;
  }
  /* ----------- Fin formulario centrado ----------- */

  #payment-form {
    margin-top: 1rem;
    font-size: 0.9rem;
  }

  #payment-form label {
    display: block;
    margin-bottom: 0.5rem;
  }

  #payment-form input[type="text"] {
    width: 100%;
    padding: 0.4rem;
    margin-bottom: 1rem;
    border: 1px solid #ccc;
    border-radius: 4px;
  }

  #payment-form input[type="radio"] {
    margin-right: 0.3rem;
  }

  /* Modal Ticket */
  #ticket-modal {
    position: fixed;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) scale(0);
    background: white;
    border-radius: 10px;
    padding: 1.5rem 2rem;
    box-shadow: 0 2px 10px rgba(0,0,0,0.25);
    z-index: 2000;
    width: 90vw;
    max-width: 420px;
    max-height: 80vh;
    overflow-y: auto;
    transition: transform 0.3s ease;
  }

  #ticket-modal.open {
    transform: translate(-50%, -50%) scale(1);
  }

  #ticket-modal pre {
    white-space: pre-wrap;
    word-wrap: break-word;
    font-family: monospace;
    font-size: 1rem;
  }

  #close-ticket-btn {
    margin-top: 1rem;
    display: block;
    width: 100%;
  }

  @media (max-width: 600px) {
    .menu-grid {
      grid-template-columns: 1fr;
    }
    #carrito {
      width: 90vw;
    }
  }
</style>
</head>
<body>

<header>
  <h1>
    <img src="https://st.depositphotos.com/69794208/59156/v/450/depositphotos_591562358-stock-illustration-initial-letter-restaurant-logo-template.jpg" alt="Logo Restaurante" />
    Gourmet Elegante
  </h1>
  <nav role="navigation" aria-label="Navegación principal">
    <a href="#" class="tab-link active" data-tab="inicio" aria-pressed="true">Inicio</a>
    <a href="#" class="tab-link" data-tab="menu" aria-pressed="false">Menú</a>
    <a href="#" class="tab-link" data-tab="ubicacion" aria-pressed="false">Ubicación</a>
    <a href="#" class="tab-link" data-tab="contacto" aria-pressed="false">Contacto</a>
    <button id="open-cart" aria-haspopup="true" aria-controls="carrito" aria-expanded="false">Carrito (<span id="cart-count">0</span>)</button>
  </nav>
</header>

<section id="inicio" class="container tabs active" tabindex="0" aria-label="Bienvenida">
  <h2>Bienvenido a Gourmet Elegante</h2>
  <p>
    En Gourmet Elegante ofrecemos una experiencia culinaria única en un ambiente sofisticado y acogedor.<br>
    Fundado en 2010, nuestro restaurante combina sabores clásicos con técnicas modernas para garantizar la máxima calidad en cada plato.
  </p>
  <img src="https://hips.hearstapps.com/hmg-prod/images/restaurante-atmosphere-burj-khalifa-dubai-elle-gourmet-64ca2f7b3445e.jpg?crop=0.668xw:1.00xh;0.317xw,0&resize=640:*" alt="Ambiente elegante del restaurante" />
</section>

<section id="menu" class="container tabs" tabindex="0" aria-label="Menú del restaurante">
  <h2>Menú Destacado</h2>
  <div role="group" aria-label="Filtros de menú">
    <button class="filter-btn active" data-cat="todos" aria-pressed="true">Todos</button>
    <button class="filter-btn" data-cat="entradas" aria-pressed="false">Entradas</button>
    <button class="filter-btn" data-cat="platos" aria-pressed="false">Platos</button>
    <button class="filter-btn" data-cat="postres" aria-pressed="false">Postres</button>
    <button class="filter-btn" data-cat="bebidas" aria-pressed="false">Bebidas</button>
  </div>
  <div class="menu-grid" id="menu-grid" aria-live="polite" aria-atomic="true"></div>
</section>

<section id="ubicacion" class="container tabs" tabindex="0" aria-label="Ubicación del restaurante">
  <h2>Ubicación</h2>
  <p>Colegio Joseph, C. Antigua Panamericana, San Salvador</p>
  <iframe 
    src="https://maps.google.com/maps?q=Colegio%20Joseph%2C%20C.%20Antigua%20Panamericana%2C%20San%20Salvador&t=&z=13&ie=UTF8&iwloc=&output=embed"
    width="100%" height="300" style="border:0;border-radius:8px;" aria-label="Mapa de ubicación"></iframe>
</section>

<section id="contacto" class="container tabs" tabindex="0" aria-label="Formulario de contacto">
  <h2>Contacto</h2>
  <form id="contact-form" aria-describedby="contact-desc">
    <p id="contact-desc">Si tienes alguna consulta o deseas reservar, completa el formulario y te contactaremos a la brevedad.</p>
    <label for="nombre">Nombre:
      <input type="text" id="nombre" name="nombre" required aria-required="true" />
    </label>
    <label for="email">Correo Electrónico:
      <input type="email" id="email" name="email" required aria-required="true" />
    </label>
    <label for="mensaje">Mensaje:
      <textarea id="mensaje" name="mensaje" rows="4" required aria-required="true"></textarea>
    </label>
    <button class="btn" type="submit">Enviar</button>
  </form>
</section>

<div id="carrito" aria-label="Carrito de compras" role="region" aria-live="polite" aria-atomic="true" aria-hidden="true">
  <button id="btn-close" class="btn" aria-label="Cerrar carrito">Cerrar 🛒</button>
  <h2>Tu Orden</h2>
  <div class="cart-items" id="cart-items"></div>
  <div><strong>Total:</strong> $<span id="cart-total">0.00</span></div>

  <form id="payment-form" aria-label="Formulario de pago">
    <label for="customer-name">Nombre del Cliente:</label>
    <input type="text" id="customer-name" name="customer-name" required placeholder="Tu nombre" aria-required="true" />

    <fieldset>
      <legend>Método de Pago:</legend>
      <label><input type="radio" name="payment-method" value="Efectivo" checked /> Efectivo</label><br>
      <label><input type="radio" name="payment-method" value="Tarjeta" /> Tarjeta</label>
    </fieldset>
  </form>

  <button id="btn-order" class="btn" aria-label="Finalizar y ordenar">Ordenar Ahora</button>
  <button id="export-btn" class="btn" style="margin-top:10px;" aria-label="Exportar datos de clientes">Exportar Base de Clientes</button>
</div>

<!-- Modal para mostrar ticket -->
<div id="ticket-modal" role="dialog" aria-modal="true" aria-labelledby="ticket-title" aria-hidden="true" style="display:none;">
  <h2 id="ticket-title">Factura Virtual</h2>
  <pre id="ticket-content"></pre>
  <button id="close-ticket-btn" class="btn" aria-label="Cerrar factura">Cerrar</button>
</div>

<footer>
  © 2025 Gourmet Elegante – Todos los derechos reservados
  <div class="socials" aria-label="Redes sociales">
    <a href="https://www.instagram.com/colegioiosephofficial/" target="_blank" rel="noopener" aria-label="Instagram" title="Instagram">📸</a>
    <a href="https://www.facebook.com/ColegioIosephMJ/?locale=es_LA" target="_blank" rel="noopener" aria-label="Facebook" title="Facebook">📘</a>
    <a href="https://www.youtube.com/@iosephtv4555" target="_blank" rel="noopener" aria-label="YouTube" title="YouTube">▶️</a>
  </div>
</footer>

<!-- Librerías externas para PDF y Excel -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/html2pdf.js/0.10.1/html2pdf.bundle.min.js"></script>
<script src="https://cdn.sheetjs.com/xlsx-latest/package/dist/xlsx.full.min.js"></script>

<script>
  // Navegación pestañas
  document.querySelectorAll('.tab-link').forEach(link => {
    link.addEventListener('click', e => {
      e.preventDefault();
      document.querySelectorAll('.tab-link').forEach(l => {
        l.classList.remove('active');
        l.setAttribute('aria-pressed', 'false');
      });
      link.classList.add('active');
      link.setAttribute('aria-pressed', 'true');

      document.querySelectorAll('.tabs').forEach(tab => tab.classList.remove('active'));
      document.getElementById(link.dataset.tab).classList.add('active');
    });
  });

  // Datos del menú con imágenes actualizadas
  const items = [
    {id:1, name:'Bruschetta', cat:'entradas', price:5.5, img:'https://www.sanpellegrino.com/es/sites/g/files/xknfdk2326/files/bruschetta_0.jpg'},
    {id:2, name:'Ensalada César', cat:'entradas', price:6.0, img:'https://newmansown.com/wp-content/uploads/2022/03/Caesar-salad-with-croutons.jpg'},
    {id:3, name:'Filete a la Parrilla', cat:'platos', price:15.5, img:'https://www.natusal.com.co/wp-content/uploads/2019/06/POST-5-PAG-2.jpg'},
    {id:4, name:'Pasta Alfredo', cat:'platos', price:13.0, img:'https://savorrecipes.com/wp-content/uploads/2022/04/Pasta-Alfredo.jpg'},
    {id:5, name:'Tiramisú', cat:'postres', price:7.0, img:'https://media.istockphoto.com/id/1248489319/es/foto/pastel-tiramis%C3%BA-con-menta.jpg?s=612x612&w=0&k=20&c=sPrndjNK3YHHjr_VrtG8eP4Z7nuJdRZPn8h-lejlxIc='},
    {id:6, name:'Helado Artesanal', cat:'postres', price:5.0, img:'https://mejisa.com/wp-content/uploads/2019/04/helado-artesanal.jpg'},
    {id:7, name:'Vino Tinto', cat:'bebidas', price:8.5, img:'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRtnwPbTBCOSQXCNlyLttlGpJYjCiAUdCIghw&s'},
    {id:8, name:'Café Espresso', cat:'bebidas', price:3.5, img:'https://s3.ppllstatics.com/diariovasco/www/multimedia/2024/11/13/espresso-RrCckvN0LEAFk54KAQQPcXM-1200x840@Diario%20Vasco.jpg'}
  ];

  const menuGrid = document.getElementById('menu-grid');

  function renderMenu(filter = 'todos') {
    menuGrid.innerHTML = '';
    const filtered = filter === 'todos' ? items : items.filter(i => i.cat === filter);
    filtered.forEach(item => {
      const div = document.createElement('div');
      div.className = 'menu-item';
      div.innerHTML = `
        <img src="${item.img}" alt="${item.name}" />
        <h3>${item.name}</h3>
        <div class="menu-footer">
          <span>$${item.price.toFixed(2)}</span>
          <button class="btn add-to-cart" data-id="${item.id}" aria-label="Agregar ${item.name} al carrito">Agregar</button>
        </div>
      `;
      menuGrid.appendChild(div);
    });
  }

  renderMenu();

  document.querySelectorAll('.filter-btn').forEach(btn => {
    btn.addEventListener('click', () => {
      document.querySelectorAll('.filter-btn').forEach(b => {
        b.classList.remove('active');
        b.setAttribute('aria-pressed', 'false');
      });
      btn.classList.add('active');
      btn.setAttribute('aria-pressed', 'true');
      renderMenu(btn.dataset.cat);
    });
  });

  // Carrito
  const cart = [];
  const cartCount = document.getElementById('cart-count');
  const cartItems = document.getElementById('cart-items');
  const cartTotal = document.getElementById('cart-total');
  const carritoDiv = document.getElementById('carrito');
  const openCartBtn = document.getElementById('open-cart');
  const closeCartBtn = document.getElementById('btn-close');
  const orderBtn = document.getElementById('btn-order');
  const exportBtn = document.getElementById('export-btn');
  const paymentForm = document.getElementById('payment-form');
  const ticketModal = document.getElementById('ticket-modal');
  const ticketContent = document.getElementById('ticket-content');
  const closeTicketBtn = document.getElementById('close-ticket-btn');

  function updateCartUI() {
    cartItems.innerHTML = '';
    if(cart.length === 0) {
      cartItems.textContent = 'El carrito está vacío.';
      cartTotal.textContent = '0.00';
      cartCount.textContent = '0';
      return;
    }
    cart.forEach(ci => {
      const item = items.find(i => i.id === ci.id);
      const div = document.createElement('div');
      div.className = 'cart-item';
      div.innerHTML = `
        <span>${item.name} x${ci.quantity}</span>
        <span>$${(item.price * ci.quantity).toFixed(2)}</span>
        <button aria-label="Eliminar ${item.name}" data-id="${item.id}">❌</button>
      `;
      cartItems.appendChild(div);
    });

    const total = cart.reduce((acc, ci) => {
      const item = items.find(i => i.id === ci.id);
      return acc + item.price * ci.quantity;
    }, 0);

    cartTotal.textContent = total.toFixed(2);
    cartCount.textContent = cart.reduce((acc, ci) => acc + ci.quantity, 0);

    // Añadir eventos para quitar producto
    cartItems.querySelectorAll('button').forEach(btn => {
      btn.onclick = () => {
        const id = Number(btn.dataset.id);
        const idx = cart.findIndex(c => c.id === id);
        if(idx !== -1) {
          cart.splice(idx,1);
          updateCartUI();
        }
      };
    });
  }

  menuGrid.addEventListener('click', e => {
    if(e.target.classList.contains('add-to-cart')){
      const id = Number(e.target.dataset.id);
      const cartItem = cart.find(ci => ci.id === id);
      if(cartItem){
        cartItem.quantity++;
      } else {
        cart.push({id, quantity:1});
      }
      updateCartUI();
    }
  });

  openCartBtn.onclick = () => {
    carritoDiv.classList.add('open');
    carritoDiv.setAttribute('aria-hidden', 'false');
    openCartBtn.setAttribute('aria-expanded', 'true');
  };
  closeCartBtn.onclick = () => {
    carritoDiv.classList.remove('open');
    carritoDiv.setAttribute('aria-hidden', 'true');
    openCartBtn.setAttribute('aria-expanded', 'false');
  };

  // Ordenar y guardar cliente
  orderBtn.onclick = () => {
    const customerName = document.getElementById('customer-name').value.trim();
    if(!customerName){
      alert('Por favor ingresa tu nombre para continuar.');
      return;
    }
    if(cart.length === 0){
      alert('El carrito está vacío.');
      return;
    }
    const paymentMethod = paymentForm.querySelector('input[name="payment-method"]:checked').value;
    const total = Number(cartTotal.textContent);

    // Guardar en localStorage
    const clients = JSON.parse(localStorage.getItem('clients') || '[]');
    clients.push({
      name: customerName,
      payment: paymentMethod,
      cart: JSON.parse(JSON.stringify(cart)),
      total,
      date: new Date().toISOString()
    });
    localStorage.setItem('clients', JSON.stringify(clients));

    // Crear contenido ticket HTML para mostrar en modal
    let ticketHTML = `<strong>*** Factura Virtual ***</strong><br><br>
      <strong>Cliente:</strong> ${customerName}<br>
      <strong>Método de Pago:</strong> ${paymentMethod}<br>
      <strong>Fecha:</strong> ${new Date().toLocaleString()}<br><br>
      <strong>Productos:</strong><br>`;

    cart.forEach(ci => {
      const item = items.find(i => i.id === ci.id);
      ticketHTML += `- ${item.name} x${ci.quantity} - $${(item.price*ci.quantity).toFixed(2)}<br>`;
    });
    ticketHTML += `<br><strong>Total a Pagar:</strong> $${total.toFixed(2)}<br><br><em>¡Gracias por su compra!</em>`;

    ticketContent.innerHTML = ticketHTML;
    ticketModal.style.display = 'block';
    ticketModal.classList.add('open');
    ticketModal.setAttribute('aria-hidden', 'false');

    // Vaciar carrito y formulario
    cart.length = 0;
    updateCartUI();
    paymentForm.reset();
  };

  closeTicketBtn.onclick = () => {
    ticketModal.style.display = 'none';
    ticketModal.classList.remove('open');
    ticketModal.setAttribute('aria-hidden', 'true');
  };

  // Exportar base de clientes a Excel
  exportBtn.onclick = () => {
    const clientsData = JSON.parse(localStorage.getItem('clients')) || [];
    if(clientsData.length === 0){
      alert('No hay registros de clientes aún.');
      return;
    }

    // Crear estructura para Excel
    const worksheetData = [
      ["Nombre", "Método de Pago", "Productos", "Total", "Fecha"]
    ];

    clientsData.forEach(record => {
      const productos = record.cart.map(ci => {
        const menuItem = items.find(i => i.id === ci.id);
        return `${menuItem.name} x${ci.quantity}`;
      }).join(", ");
      worksheetData.push([
        record.name,
        record.payment,
        productos,
        record.total.toFixed(2),
        new Date(record.date).toLocaleString()
      ]);
    });

    // Crear libro y hoja
    const wb = XLSX.utils.book_new();
    const ws = XLSX.utils.aoa_to_sheet(worksheetData);
    XLSX.utils.book_append_sheet(wb, ws, "Clientes");

    // Descargar archivo Excel
    XLSX.writeFile(wb, `BaseClientes_${Date.now()}.xlsx`);
  };

  // Actualizar UI carrito al cargar página
  updateCartUI();

  // Manejar envío formulario contacto
  const contactForm = document.getElementById('contact-form');
  contactForm.addEventListener('submit', e => {
    e.preventDefault();
    alert('Gracias por contactarnos. Te responderemos pronto.');
    contactForm.reset();
  });
</script>

</body>
</html>
