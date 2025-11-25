<script>
    export let name;
    export let description;
</script>

<div class="menu-item-card">
    <h4>{name}</h4>
    <p>{description}</p>
</div>

<style>
    .menu-item-card {
        background-color: #ffffff;
        border-radius: 8px;
        padding: 20px;
        box-shadow: 0 4px 10px rgba(0, 0, 0, 0.05);
        transition: transform 0.3s ease;
        border-left: 5px solid #daa520; /* ¡ACTUALIZADO: Dorado del corazón como borde! */
    }

    .menu-item-card:hover {
        transform: translateY(-3px);
        box-shadow: 0 6px 15px rgba(0, 0, 0, 0.1);
    }

    h4 {
        font-family: "Playfair Display", serif;
        font-size: 1.4em;
        color: #5a3f1f; /* ¡ACTUALIZADO: Marrón Oscuro para los nombres de los platos! */
        margin-top: 0;
        margin-bottom: 8px;
    }

    p {
        font-size: 1em;
        color: #555555; /* Mantiene un gris para la descripción */
        margin: 0;
    }
</style>
