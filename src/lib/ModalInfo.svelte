<script>
    import { categoria, medicamento, descripcion, imagen } from './store'
</script>
<!-- Modal -->
<div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
>
    <div class="modal-dialog">
        <div class="modal-content">
            <div class="modal-header">
                <h1 class="modal-title fs-5" id="exampleModalLabel">
                    Medicamento
                </h1>
                <button
                    type="button"
                    class="btn-close"
                    data-bs-dismiss="modal"
                    aria-label="Close"
                />
            </div>
            <div class="modal-body">
                <h4>Categoria: {$categoria}</h4>
                <h4>Medicamento: {$medicamento}</h4>
                <img src={`/${$imagen}`} alt="">
                <p>{$descripcion}</p>
            </div>
            <div class="modal-footer">
                <button
                    type="button"
                    class="btn btn-secondary"
                    data-bs-dismiss="modal">Close</button
                >
            </div>
        </div>
    </div>
</div>

<style>
    .modal {
        color: black;
    }
    .modal-body {
        text-align: center;
    }
    .modal-body img {
        width: 50%;
    }
    .modal-body p {
        text-align: justify;
    }
</style>