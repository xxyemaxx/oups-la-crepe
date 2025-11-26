<script>
    // @ts-nocheck

    import MenuItem from "$lib/components/MenuItem.svelte";
    import { menu } from "$lib/data/menu.js";

    // Datos de Contacto
    const address = "Centro Comercial Aleste"; // <-- ¡TEXTO ACTUALIZADO!
    const phone = "88483086";
    const email = "Adriana Meléndez Sánchez";

    // URL de WhatsApp para iniciar chat: https://wa.me/506 + número
    const whatsappUrl = `https://wa.me/506${phone}`;

    // URL de la ubicación de Google Maps (¡Usada para el clic!)
    const mapLocationUrl =
        "https://www.google.com/maps/place/Centro+Comercial+Aleste/@9.9153694,-84.0479068,13z/data=!4m10!1m2!2m1!1scentro+comercial+curridabat!3m6!1s0x8fa0e33f440389ef:0x7e17f73258410b6c!8m2!3d9.9216669!4d-84.0205722!15sChtjZW50cm8gY29tZXJjaWFsIGN1cnJpZGFiYXRaHSIbY2VudHJvIGNvbWVyY2lhbCBjdXJyaWRhYmF0kgEPc2hvcHBpbmdfY2VudGVymgEjQ2haRFNVaE5NRzluUzBWSlEwRm5TVVExZVV4dE0yTjNFQUXgAQD6AQQIABBJ!16s%2Fg%2F11t2rwyd3d?entry=ttu&g_ep=EgoyMDI1MTEyMy4xIKXMDSoASAFQAw%3D%3D";

    // Ruta de la imagen de fondo principal
    const heroImage = "/img/crepe-hero.jpg";
</script>

<section
    id="top"
    class="hero-section"
    style="background-image: url({heroImage});"
>
    <div class="hero-content">
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
                <h3>📍 Dirección (Haz clic para ver en Maps)</h3>
                <p>
                    <a
                        href={mapLocationUrl}
                        target="_blank"
                        class="contact-link address-link"
                    >
                        {address}
                    </a>
                </p>

                <h3>📞 Teléfonos</h3>
                <p>
                    <a href="tel:+506{phone}" class="contact-link">
                        +506 {phone} (Tocar para llamar)
                    </a>
                </p>

                <h3 class="whatsapp-title">📱 WhatsApp</h3>
                <p>
                    <a
                        href={whatsappUrl}
                        target="_blank"
                        class="contact-link whatsapp-link"
                    >
                        Enviar mensaje por WhatsApp
                    </a>
                </p>

                <h3>👤 Nombre del Contacto</h3>
                <p>{email}</p>

                <h3 class="schedule-title">🕒 Horario</h3>
                <p>Lun - Vie: N/A am - N/A pm</p>
                <p>Mie - Dom: 12:00 md - 8:00 pm</p>
            </div>
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
        background-color: rgba(0, 0, 0, 0.4);
        background-blend-mode: overlay;
        border-radius: 8px;
        overflow: hidden;
    }

    .hero-content {
        color: #ffffff;
        padding: 20px;
        position: relative;
        z-index: 2;
        max-width: 800px;
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
        justify-content: center;
        gap: 40px;
        padding: 0 20px;
    }

    .info-column {
        flex: 1;
        max-width: 800px;
    }

    .info-column h2 {
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

    /* Estilos para los enlaces de contacto (Teléfono/WhatsApp y Dirección) */
    .contact-link {
        text-decoration: none;
        color: #5a3f1f; /* Marrón Oscuro */
        font-weight: 600;
        transition: color 0.3s;
        display: block;
    }

    .contact-link:hover {
        color: #daa520; /* Dorado */
        text-decoration: underline;
    }

    .address-link {
        margin-bottom: 20px; /* Separación de este bloque al siguiente */
    }

    .whatsapp-title {
        margin-top: 25px !important;
        margin-bottom: 5px !important;
    }

    .whatsapp-link {
        background-color: #25d366; /* Verde de WhatsApp */
        color: white !important;
        padding: 8px 15px;
        border-radius: 5px;
        text-align: center;
        margin-top: 10px;
        display: inline-block;
        text-decoration: none;
        font-weight: bold;
    }

    .whatsapp-link:hover {
        background-color: #1faa54;
    }

    @media (max-width: 900px) {
        .content-wrapper {
            flex-direction: column;
            padding: 0;
        }
        .info-column {
            max-width: 100%;
        }
    }
</style>
