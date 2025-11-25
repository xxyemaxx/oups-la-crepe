<script>
    // ... (tu script actual)
</script>

<footer>
    <div class="footer-content">
        <div class="contact-info">
            <h3>CONTACTO</h3>
            <p>📍 Dirección: Del Centro Comercial Aleste en Curridabat</p>
            <p>📞 Teléfono: (506) 8848-3086</p>
            <p>👤 Nombre del Contacto: Adriana Meléndez Sánchez</p>
        </div>

        <div class="schedule">
            <h3>HORARIO</h3>
            <p>Lun - Jue: 10:00 am - 9:00 pm</p>
            <p>Vie - Sáb: 10:00 am - 9:30 pm</p>
            <p>Dom: 11:00 am - 9:00 pm</p>
        </div>

        <div class="branding">
            <p>© {new Date().getFullYear()} Oups la crêpe.</p>
            <p>La auténtica crepa francesa.</p>
        </div>
    </div>
</footer>

<style>
    footer {
        background-color: #5a3f1f; /* ¡ACTUALIZADO: Marrón Oscuro del logo para el footer! */
        color: #ffffff;
        padding: 30px 20px;
        margin-top: 50px;
        font-family: "Montserrat", sans-serif;
    }

    .footer-content {
        max-width: 1200px;
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        flex-wrap: wrap;
        gap: 30px;
    }

    h3 {
        font-family: "Playfair Display", serif;
        color: #daa520; /* ¡ACTUALIZADO: Dorado del corazón para los títulos del footer! */
        margin-top: 0;
        margin-bottom: 10px;
        text-transform: uppercase;
        font-size: 1.2em;
    }

    p {
        margin: 5px 0;
        font-size: 0.9em;
        line-height: 1.5;
    }

    .branding {
        text-align: right;
        font-size: 0.8em;
        opacity: 0.7;
    }

    @media (max-width: 768px) {
        .footer-content {
            flex-direction: column;
            align-items: center;
            text-align: center;
        }
        .branding {
            text-align: center;
            margin-top: 20px;
        }
    }
</style>
