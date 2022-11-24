<script>
    import objetivo from "../objetivo.json";
</script>

<div id="nosotros" class="nosotros">
    <h1 style="color: black; text-align: center; text-transform: uppercase; color:white;">Sobre Nosotros</h1>
    <div class="mycard">
        <div class="mytext">
            <h2>Objetivo</h2>
            <p>{objetivo.objetivo[0]}</p>
            <p>{objetivo.objetivo[1]}</p>
            <p>{objetivo.objetivo[2]}</p>
        </div>
        <div class="contacto-nosotros">
            <h2>Contacto</h2>
            <p style="font-size: 1.4rem;text-align:left;margin-left:1rem;">Telefonos: </p>
            <ul class="ul-contacto">
                <li>{objetivo["Número de contacto"][0]}</li>
                <li>{objetivo["Número de contacto"][1]}</li>
                <li>{objetivo["Número de contacto"][2]}</li>
                <li>{objetivo["Número de contacto"][3]}</li>
                <li>{objetivo["Número de contacto"][4]}</li>
            </ul>

            <p style="font-size: 1.4rem;text-align:left;margin-left:1rem;">Correo: </p>
            <ul class="ul-contacto">
                <li>{objetivo.Correo}</li>
            </ul>
        </div>
    </div>
</div>

<style>
    .nosotros {
        border-color: white;
        border: 1px solid black;
        width: 100%;
        padding: 2rem;
        background-color: rgb(4, 185, 218);
    }
    .mycard {
        display: flex;
        column-gap: 1rem;

        width: 70%;
        border: 1px solid rgb(207, 207, 207);
        border-radius: 5px;
        margin: 1rem auto;
        text-align: center;
        padding: 10px;
        background-color: rgb(3, 88, 121);
    }
    .mytext h2 {
        color: white;
        text-align: left;
    }
    .mytext p{
        text-align: justify;
    }
    .ul-contacto {
        list-style: none;
        text-align: left;
    }
    .ul-contacto li {
        text-align: left;
    }
    .mytext, .contacto-nosotros {
        width: 50%;
    }
</style>
