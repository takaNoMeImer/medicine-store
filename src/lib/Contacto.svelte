<script>
</script>

<div id="contacto" class="contacto">
    <p class="myheader-form">Formulario de Contacto</p>
    <div class="mycontainer">
        <div class="myleft-side">
            <img src="/light2.png" alt="">
        </div>
        <div class="mtright-side">
            <p style="font-size: 3rem;">Contacto</p>
            <div class="mycontrol">
                <input type="text" placeholder="Nombre">
            </div>
            <div class="mycontrol">
                <input type="text" placeholder="Correo">
            </div>
            <div class="mycontrol">
                <input type="text" placeholder="Asunto">
            </div>
            <div class="mycontrol">
                <textarea name="mensaje" id="mensaje" cols="30" rows="2" placeholder="Mensaje"></textarea>
            </div>
            <div class="mycontrol">
                <button>Enviar</button>
            </div>
        </div>
    </div>
</div>

<style>
    .contacto {
        border-color: white;
        border: 1px solid black;
        width: 100%;
        background-image: url('/image.jpg');
        background-repeat: no-repeat;
		background-size: cover;
		background-position: center;
    }
    .myheader-form {
        font-size: 3rem;
        text-align: center;
        color: black;
        -webkit-text-stroke: 1px white;
    }
    .mycontainer {
        border-radius: 8px;
        color: black;
        padding: 10px;
        display: flex;
        width: 80%;
        border: 1px solid rgb(230, 230, 230);
        margin: 0 auto;
        margin-bottom: 2rem;
        background-color: #fff;
    }
    .myleft-side img {
        width: 90%;
    }
    .mtright-side {
        text-align: center;
    }
    .myleft-side, .mtright-side {
        width: 50%;
    }
    .mtright-side p {
        color: rgb(0, 255, 98);
    }
    .mycontrol input{
        padding: 12px;
        width: 90%;
        font-size: 1.4rem;
        border-radius: 4px;
        outline: none;
        margin-bottom: 1rem;
    }
    .mycontrol input:focus {
        border: 0.8px solid rgb(87, 165, 255);
        box-shadow: 0 0 5px 0.5px rgb(82, 82, 255);
    }
    .mycontrol button {
        width: 90%;
        background-color: rgb(1, 219, 85);
        color: white;
        padding: 12px;
        border-radius: 4px;
        border: 0.8px solid rgb(0, 255, 98);
    }
    .mycontrol button:hover {
        transform: scale(.99);
        background-color: rgb(3, 192, 76);
    }
    textarea {
        width: 90%;
        font-size: 1.4rem;
        border-radius: 4px;
        outline: none;
    }
    textarea:focus {
        border: 0.8px solid rgb(87, 165, 255);
        box-shadow: 0 0 5px 0.5px rgb(82, 82, 255);
    }
    @media (max-width: 520px) {
        .myleft-side {
            display: none;
        }
        .mtright-side {
            width: 100%;
        }
    }
</style>