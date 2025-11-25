<script>
    // @ts-nocheck

    import MenuItem from "$lib/components/MenuItem.svelte";
    import { menu } from "$lib/data/menu.js";

    // Datos de Contacto (ACTUALIZADOS)
    const address = "Del Centro Comercial Aleste en Curridabat";
    const phone = "8848-3086";
    const email = "Adriana Meléndez Sánchez"; // Nombre de contacto

    // URL de ejemplo para el mapa
    const mapIframeUrl =
        "https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3930.298715764724!2d-84.1481177!3d9.923838!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4e13.1!3m3!1m2!1s0x8fa0e41776510a7b%3A0x81152a5518b53272!2sMultiplaza%20Escaz%C3%BA!5e0!3m2!1ses-419!2scr!4v1678229971844!5m2!1ses-419!2scr";

    // Rutas de Imágenes (VERIFICA que estas rutas y extensiones coincidan con tus archivos en static/img/)
    // Reemplaza .jpg por .png si tienes el logo con fondo transparente.
    const logoHero = "/img/oups-logo.jpg";
    const heroImage = "/img/crepe-hero.jpg";
</script>

<section
    id="top"
    class="hero-section"
    style="background-image: url({heroImage});"
>
    <div class="hero-content">
        <img
            src={logoHero}
            alt="Logo Oups la crêpe"
            class="hero-logo-overlay"
        />

        <h1>Oups la crêpe</h1>
        <p>La auténtica crepa francesa en su máxima expresión.</p>
        <a href="#menu" class="cta-button">Ver Menú Completo</a>
    </div>
</section>

<section class="intro-section">
    <div class="intro-text">
        <h2>Nuestra Promesa</h2>
        <p>
            En Oups la crêpe, los mejores secretos de la alta cocina francesa se
            fusionan con la calidad y la frescura, creando un ambiente moderno y
            de vanguardia para tu deleite.
        </p>
        <p>
            Ofrecemos una alternativa de comida deliciosa, preparada con
            ingredientes de primera, que sin duda, podrá satisfacer hasta el
            gusto más exigente. **¡Una experiencia que te hará decir "Oups"!**
        </p>
    </div>
</section>

<section id="menu" class="menu-page">
    <div class="menu-header">
        <h1>El Menú de Oups la crêpe</h1>
        <p>
            Explora nuestras crepas dulces y saladas inspiradas en la tradición
            francesa.
        </p>
    </div>

    {#each menu as section}
        <div class="menu-category">
            <h2>{section.category}</h2>
            <div class="menu-grid">
                {#each section.items as item}
                    <MenuItem name={item.name} description={item.description} />
                {/each}
            </div>
        </div>
    {/each}
</section>

<section id="contacto" class="contact-page">
    <div class="header-section">
        <h1>Contáctanos</h1>
        <p>Estamos listos para atender tus consultas o recibir tus pedidos.</p>
    </div>

    <div class="content-wrapper">
        <div class="info-column">
            <h2>Nuestra Ubicación</h2>

            <div class="details">
                <h3>📍 Dirección</h3>
                <p>{address}</p>

                <h3>📞 Teléfonos</h3>
                <p>{phone}</p>

                <h3>👤 Nombre del Contacto</h3>
                <p>{email}</p>

                <h3 class="schedule-title">🕒 Horario</h3>
                <p>Lun - Jue: 10:00 am - 9:00 pm</p>
                <p>Vie - Sáb: 10:00 am - 9:30 pm</p>
                <p>Dom: 11:00 am - 9:00 pm</p>
            </div>

            <iframe
                src={mapIframeUrl}
                width="100%"
                height="300"
                style="border:0;"
                allowfullscreen=""
                loading="lazy"
                referrerpolicy="no-referrer-when-downgrade"
                title="Ubicación de Oups la crêpe"
            >
            </iframe>
        </div>

        <div class="form-column">
            <h2>Envíanos un Mensaje</h2>
            <form
                on:submit|preventDefault={() =>
                    alert("Mensaje enviado (simulado)")}
            >
                <div class="form-group">
                    <label for="name">Nombre Completo</label>
                    <input type="text" id="name" required />
                </div>
                <div class="form-group">
                    <label for="email">Correo Electrónico</label>
                    <input type="email" id="email" required />
                </div>
                <div class="form-group">
                    <label for="message">Tu Mensaje</label>
                    <textarea id="message" rows="5" required></textarea>
                </div>
                <button type="submit" class="submit-button"
                    >Enviar Mensaje</button
                >
            </form>
        </div>
    </div>
</section>

<style>
    /* COLORES DE LA PALETA: 
       - Marrón Oscuro (#5A3F1F)
       - Dorado (#DAA520)
       - Texto Oscuro (#222222)
    */

    /* ------------------- Hero Section (TOP) ------------------- */
    .hero-section {
        height: 70vh;
        background-size: cover;
        background-position: center;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        margin-bottom: 40px;
        position: relative;
        /* Superposición oscura para que el texto blanco resalte */
        background-color: rgba(0, 0, 0, 0.4);
        background-blend-mode: overlay;
        border-radius: 8px;
        overflow: hidden;
    }

    .hero-content {
        color: #ffffff;
        padding: 20px;
        position: relative;
        z-index: 2; /* Asegura que el texto esté sobre el logo */
        max-width: 800px;
    }

    /* AJUSTES PARA EL LOGO MARCA DE AGUA (para que se vea sutil y centrado) */
    .hero-logo-overlay {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        /* Tamaño para marca de agua */
        width: 300px;
        max-width: 80%;
        height: 300px;

        /* Opacidad baja para el efecto sutil */
        opacity: 0.1;

        object-fit: contain;
        z-index: 1;
        pointer-events: none;
    }

    .hero-content h1 {
        font-size: 4em;
        margin-bottom: 0.1em;
        color: #ffffff;
        text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);
    }

    .hero-content p {
        font-size: 1.5em;
        font-weight: 300;
        margin-bottom: 1.5em;
    }

    .cta-button {
        display: inline-block;
        background-color: #daa520; /* Dorado */
        color: #ffffff;
        padding: 12px 30px;
        text-decoration: none;
        font-size: 1.2em;
        border-radius: 5px;
        transition:
            background-color 0.3s,
            transform 0.2s;
        text-transform: uppercase;
        font-weight: bold;
        letter-spacing: 1px;
    }

    .cta-button:hover {
        background-color: #c08e17; /* Dorado más oscuro al pasar el ratón */
        transform: translateY(-2px);
    }

    /* ------------------- Intro Section ------------------- */
    .intro-section {
        padding: 20px 0 60px 0;
        text-align: center;
    }

    .intro-text {
        max-width: 800px;
        margin: 0 auto;
        line-height: 1.6;
    }

    .intro-text h2 {
        font-size: 2em;
        margin-bottom: 10px;
        color: #5a3f1f; /* Marrón Oscuro */
    }

    .intro-text p {
        font-size: 1.1em;
        margin-bottom: 20px;
    }

    /* ------------------- Menu Page ------------------- */
    .menu-page {
        padding: 40px 0;
    }

    .menu-header {
        text-align: center;
        margin-bottom: 40px;
    }

    .menu-header h1 {
        font-size: 3em;
    }

    .menu-category {
        margin-bottom: 60px;
    }

    .menu-category h2 {
        font-size: 2.2em;
        text-align: left;
        border-bottom: 2px solid #daa520; /* Dorado como línea divisoria */
        padding-bottom: 5px;
        margin-top: 0;
        margin-left: 20px;
    }

    .menu-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
        gap: 30px;
        padding: 0 20px;
    }

    /* ------------------- Contact Page ------------------- */
    .contact-page {
        padding: 40px 0 60px 0;
    }

    .content-wrapper {
        display: flex;
        gap: 40px;
        padding: 0 20px;
    }

    .info-column,
    .form-column {
        flex: 1;
    }

    .info-column h2,
    .form-column h2 {
        text-align: left;
        color: #5a3f1f; /* Marrón Oscuro */
        border-bottom: 2px solid #daa520; /* Dorado */
        padding-bottom: 5px;
        margin-bottom: 30px;
    }

    .details h3 {
        font-family: "Montserrat", sans-serif;
        color: #daa520; /* Dorado para los títulos de detalle de contacto */
        font-size: 1.1em;
        margin-top: 15px;
        margin-bottom: 5px;
        font-weight: 600;
    }

    iframe {
        border-radius: 8px;
        margin-top: 20px;
        box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    }

    .form-group {
        margin-bottom: 20px;
    }

    label {
        display: block;
        margin-bottom: 5px;
        font-weight: 500;
        color: #222222; /* Texto Oscuro */
    }

    input,
    textarea {
        width: 100%;
        padding: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
        box-sizing: border-box;
        font-size: 1em;
        font-family: "Montserrat", sans-serif;
    }

    .submit-button {
        background-color: #daa520; /* Dorado */
        color: white;
        padding: 12px 25px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 1.1em;
        font-weight: bold;
        transition: background-color 0.3s;
        text-transform: uppercase;
    }

    .submit-button:hover {
        background-color: #c08e17; /* Dorado más oscuro al pasar el ratón */
    }

    @media (max-width: 900px) {
        .content-wrapper {
            flex-direction: column;
            padding: 0;
        }
    }

    @media (max-width: 768px) {
        .hero-logo-overlay {
            width: 250px;
            height: 250px;
        }
    }
</style>
