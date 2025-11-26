<script>
    // Lista de enlaces de navegación (¡GALERÍA HA SIDO ELIMINADA!)
    const navLinks = [
        { name: "INICIO", path: "#top" },
        { name: "MENÚ", path: "#menu" },
        { name: "CONTACTO", path: "#contacto" },
    ];

    // Ruta del logo. Asegúrate de que esta ruta coincida con el nombre de tu archivo en static/img/
    const headerLogo = "/img/oups-logo.jpg";
</script>

<header>
    <div class="logo">
        <a href="#top">
            <img
                src={headerLogo}
                alt="Oups la crêpe Logo"
                class="header-logo-img"
            />
        </a>
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
    - Marrón Oscuro (Texto principal/Logo): #5A3F1F
    - Dorado (Acento/Corazón): #DAA520
    */

    header {
        background-color: #ffffff;
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
        border-bottom: 3px solid #f8f4ec;
    }

    .logo a {
        /* Estilos de enlace para el logo de imagen */
        text-decoration: none;
        transition: opacity 0.3s;
        display: flex;
        align-items: center;
    }

    .logo a:hover {
        opacity: 0.8; /* Efecto de desvanecimiento sutil al pasar el ratón */
    }

    /* ESTILOS CLAVE: AJUSTE DE TAMAÑO PARA EL LOGO EN EL HEADER */
    .header-logo-img {
        height: 65px; /* ¡TAMAÑO ACTUALIZADO! Logo más grande en la esquina */
        width: auto;
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
        .header-logo-img {
            height: 45px; /* Ajuste del tamaño del logo para móviles */
        }
        nav a {
            font-size: 0.9em;
        }
    }
</style>
