<script>
    // Ya no es necesario importar 'page' si solo usamos enlaces estáticos.

    // Lista de enlaces de navegación (sin Galería)
    const navLinks = [
        { name: "INICIO", path: "#top" },
        { name: "MENÚ", path: "#menu" },
        { name: "CONTACTO", path: "#contacto" },
    ];
</script>

<header>
    <div class="logo">
        <a href="#top">Oups la crêpe</a>
    </div>

    <nav>
        <ul>
            {#each navLinks as link}
                <li>
                    <a href={link.path}>
                        {link.name}
                    </a>
                </li>
            {/each}
        </ul>
    </nav>
</header>

<style>
    /* Paleta de colores del logo:
    - Fondo (Base): #F8F4EC (Crema)
    - Marrón Oscuro (Texto principal/Logo): #5A3F1F
    - Dorado (Acento/Corazón): #DAA520
    - Negro Oscuro (Texto secundario): #222222
    */

    header {
        background-color: #ffffff; /* Fondo blanco para contraste */
        color: #222222;
        padding: 10px 40px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        z-index: 100;
        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
        border-bottom: 3px solid #f8f4ec; /* Línea suave color crema */
    }

    .logo a {
        font-family: "Playfair Display", serif;
        font-size: 1.8em;
        font-weight: bold;
        color: #5a3f1f; /* Marrón Oscuro */
        text-decoration: none;
        transition: color 0.3s;
    }

    .logo a:hover {
        color: #daa520; /* Dorado al pasar el ratón */
    }

    nav ul {
        list-style: none;
        margin: 0;
        padding: 0;
        display: flex;
        gap: 25px;
    }

    nav a {
        text-decoration: none;
        color: #222222;
        font-size: 1em;
        font-weight: 500;
        padding: 5px 0;
        position: relative;
        transition: color 0.3s;
    }

    /* Línea de acento debajo del enlace */
    nav a::after {
        content: "";
        position: absolute;
        bottom: -5px;
        left: 0;
        width: 0;
        height: 3px;
        background-color: #daa520; /* Dorado */
        transition: width 0.3s ease-out;
    }

    /* Efecto al pasar el ratón */
    nav a:hover {
        color: #5a3f1f; /* Marrón Oscuro */
    }

    nav a:hover::after {
        width: 100%;
    }

    /* Media query para móviles */
    @media (max-width: 768px) {
        header {
            padding: 10px 20px;
        }
        nav ul {
            gap: 15px;
        }
        .logo a {
            font-size: 1.5em;
        }
        nav a {
            font-size: 0.9em;
        }
    }
</style>
