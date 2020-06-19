# III
Código de Master Details


@{
    Layout = null;
}

<!DOCTYPE html>

<html>
<head>
    <meta name="viewport" content="width=device-width" />
    <title>Maestro Detalle</title>
    <link href="~/Content/uikit.css" rel="stylesheet" />
    <link href="~/Content/select2.min.css" rel="stylesheet" />
    <link href="~/Content/bootstrap.min.css" rel="stylesheet" />
    <link href="~/Content/jquery.dataTables.min.css" rel="stylesheet" />
    <link href="~/Content/animate.css" rel="stylesheet" />
    <link href="~/Content/Site.css" rel="stylesheet" />
    <script src="~/Scripts/jquery-3.3.1.min.js"></script>
</head>
<body>
    <div class="uk-container uk-container-center" id="epn_container">
        <div class="menu__top">
            <ul class="menu" data-uk-switcher="{connect:'#my-id', animation: 'uk-animation-fade, uk-animation-slide-left'}">
                <li aria-expanded="true" class="uk-active">
                    <a href="">
                        Inicio
                    </a>
                </li>
                <li aria-expanded="false" class="">
                    <a href="">
                        Formatos
                    </a>
                </li>
                <li aria-expanded="false" class="">
                    <a href="">
                        Reportes
                    </a>
                </li>
            </ul>
            <!-- This is the container of the content items -->
            <ul id="my-id" class="uk-switcher">
                <li aria-hidden="false" class="uk-active" style="animation-duration: 200ms;">
                    <div class="uk-btn-group">
                        <a class="uk-margin-top-modificado" href="#" id="flecha_izquierda">
                            <i class="uk-icon-large uk-icon-arrow-left"></i>
                        </a>
                        <a class="uk-margin-top-modificado" href="#" id="flecha_derecha">
                            <i class="uk-icon-large uk-icon-arrow-right"></i>
                        </a>
                        <a id="btn_guardar">
                            <i class="uk-icon-large uk-icon-save">
                            </i><br>Guardar
                        </a>
                        <a href="#" id="btn_nuevo">
                            <i class="uk-icon-large uk-icon-file-o">
                            </i><br>Nuevo
                        </a>
                        <a href="#" id="btn_cancel">
                            <i class="uk-icon-large uk-icon-ban">
                            </i><br>Cancelar
                        </a>
                        <a href="#" id="btn_imprimir">
                            <i class="uk-icon-large uk-icon-print">
                            </i><br>Imprimir
                        </a>
                        <a href="#" id="btn_listado" data-toggle="modal" data-target="#ModalFacturas">
                            <i class="uk-icon-large uk-icon-list-ul">
                            </i><br>
                            Listado
                        </a>
                        <a href="#" id="btn_eliminar">
                            <i class="uk-icon-large uk-icon-trash">
                            </i><br>
                            Eliminar
                        </a>
                    </div>
                </li>
                <li aria-hidden="true" class="" style="animation-duration: 200ms;">
                    <div class="uk-btn-group">
                        <a href="#" id="btn_imprimir_pos">
                            <i class="uk-icon-large uk-icon-print">
                            </i><br>
                            POS
                        </a>
                        <a href="#" id="btn_imprimir_media_carta">
                            <i class="uk-icon-large uk-icon-print">
                            </i><br>
                            Med. Cart
                        </a>
                        <a href="#" id="btn_imprimir_carta">
                            <i class="uk-icon-large uk-icon-print">
                            </i><br>
                            Carta
                        </a>
                    </div>
                </li>
                <li aria-hidden="true" class="" style="animation-duration: 200ms;">
                    <div class="uk-btn-group">
                        <a href="#" id="btn_resumen">
                            <i class="uk-icon-large uk-icon-bar-chart">
                            </i><br>
                            Resumen
                        </a>
                    </div>
                </li>
            </ul>
        </div>

        <section id="uk-top-a" class="bg__top_a">
            <div class="uk-clearfix">
                <div class="uk-float-left">
                    <label class="uk-label color-white" for="suplidor">
                        Persona
                    </label>
                    <select name="personas" id="personas" class="form-control" style="width:280px;">
                        @*Aquí se llena automático desde el servidor por Java Script*@
                    </select>
                    <a class="color-white force-color" data-toggle="modal" data-target="#ModalPersona">
                        <i class="uk-icon-large uk-icon-plus-square-o">
                        </i><br>
                    </a>
                </div>
                <div class="uk-float-right">
                    <label class="uk-label color-white">
                        Tipo de Orden
                    </label>
                    <select name="Tipos_de_Orden" id="Tipos_de_Orden" class="form-control" style="width:280px;">
                        @*Aquí se llena automático desde el servidor por Java Script*@
                    </select>
                    <a class="color-white force-color" data-toggle="modal" data-target="#ModalTipoDeOrden">
                        <i class="uk-icon-large uk-icon-plus-square-o">
                        </i><br>
                    </a>
                </div>
            </div>
        </section>
        <section id="uk-top-b">
            <div class="uk-grid uk-grid-medium uk-margin-top" data-uk-grid-margin="">
                <div class="uk-width-medium-7-10 uk-width-small-1-2 uk-row-first">
                    <!--LEFT-->
                    <div class="uk-form-row">
                        <label>Datos:</label>
                        <br />
                        <textarea id="text_persona" class="" rows="4" cols="44"></textarea>
                    </div>
                </div>
                <div class="uk-width-medium-3-10 uk-width-small-1-2">
                    <!--RIGHT-->
                    <div class="uk-grid uk-grid-small" data-uk-grid-margin="">
                        <div class="uk-width-medium-1-2 uk-row-first">
                            <label class="uk-text-small">
                                FECHA
                            </label>
                            <div class="uk-form-icon">
                                <i class="uk-icon-calendar">
                                </i>
                                <input id="txt_fecha" class="form-control" type="date" name="txt_fecha" placeholder="01/01/2020" data-uk-datepicker="{format:'DD/MM/YYYY'}">
                            </div>
                        </div>
                        <div class="uk-width-medium-1-2 uk-grid-margin">
                            <label class="uk-text-small">
                                ID DOCUMENTO
                            </label>
                            <input type="text" id="id_orden" placeholder="AUTO" class="form-control">
                            <label class="uk-text-small">
                                Condiciones
                            </label>
                            <table>
                                <tr>
                                    <td>
                                        <div class="row">
                                            <div class="col-md-8">
                                                <select class="uk-width-1-1" placeholder="Condiciones" name="condiciones" id="condiciones">
                                                    @*Aquí se llena automático desde el servidor por Java Script*@
                                                </select>
                                            </div>
                                            <div class="col-md-1">
                                                <a class="btn_crear_producto" href="#" data-toggle="modal" data-target="#ModalCondiciones">
                                                    <i class="uk-icon-large uk-icon-plus-square-o"></i><br>
                                                </a>
                                            </div>
                                        </div>
                                    </td>
                                </tr>
                            </table>
                        </div>
                    </div>
                </div>
            </div>
        </section>
        <section class="uk-margin-top">
            <table>
                <tr>
                    <td>
                        <select name="Producto_Codigo" id="Producto_Codigo" class="form-control" style="width:160px;">
                            @*Aquí se llena automático desde el servidor por Java Script*@
                        </select>
                    </td>
                    <td>
                        <div class="uk-margin-left">
                            <a class="btn_crear_producto" href="#" data-toggle="modal" data-target="#ModalCrearProducto">
                                <i class="uk-icon-large uk-icon-plus-square-o"></i><br>
                            </a>
                        </div>
                    </td>
                    <td>
                        <div class="uk-margin-left">
                            <select name="Producto_Descripcion" id="Producto_Descripcion" class="form-control" style="width:320px;">
                                @*Aquí se llena automático desde el servidor por Java Script*@
                            </select>
                        </div>
                    </td>
                    <td>
                        <div class="uk-margin-left">
                            <input style="text-align:right; width:150px" type="text" name="Cantidad" id="Cantidad" value="0.00" class="form-control" />
                        </div>
                    </td>
                    <td>
                        <div class="uk-margin-left">
                            <input style="text-align:right; width:150px" type="text" name="Precio" id="Precio" value="0.00" class="form-control" />
                        </div>
                    </td>
                    <td>
                        <div class="uk-margin-left">
                            <a href="#" id="btn_agregar_producto">
                                <i class="uk-icon-large uk-icon-plus-square-o"></i><br>
                            </a>
                        </div>
                    </td>
                    <td>
                        <div class="uk-margin-left">
                            <input type="text" readonly="readonly" name="text_Impuesto" id="text_Impuesto" style="text-align:right; width:80px; background-color:white" class="form-control" />
                        </div>
                    </td>
                </tr>
            </table>
        </section>
        <section class="uk-margin-top" id="ReferenciaTabla">
            <table class="table table-striped" id="tablaDetalle">
                <thead>
                    <tr>
                        <th>Id</th>
                        <th>Código</th>
                        <th>Descripción</th>
                        <th class="text-right">Cantidad</th>
                        <th class="text-right">Precio</th>
                        <th class="text-right">Impuesto</th>
                        <th class="text-right">Monto</th>
                        <th></th>
                    </tr>
                </thead>
                <tbody></tbody>
            </table>
        </section>
        <section class="row uk-margin-bottom">
            <div class="col-md-6 text-left">
                <label>Comentarios:</label>
                <textarea class="form-control" rows="4" cols="30" name="comentarios" id="comentarios"></textarea>
            </div>
            <div class="col-md-6 text-right">
                <div class="uk-subtotal">
                    <label>Subtotal</label>
                    <input type="text" readonly="readonly" name="txt_subtotal" id="txt_subtotal" value="0.00" class="text-right" />
                </div>
                <div class="uk-impuesto">
                    <label>Impuestos</label>
                    <input type="text" readonly="readonly" name="txt_impuestos" id="txt_impuestos" value="0.00" class="text-right" />
                </div>

                <div class="uk-total">
                    <label>Total</label>
                    <input type="text" readonly="readonly" name="txt_total" id="txt_total" value="0.00" class="text-right" />
                </div>
            </div>
        </section>
    </div>
    <div class="loaderbody" id="loaderbody">
        <div class="loader" id="loader"></div>
    </div>
    <script src="~/Scripts/bootstrap.min.js"></script>
    <script src="~/Scripts/uikit.min.js"></script>
    <script src="~/Scripts/select2.min.js"></script>
    <script src="~/Scripts/sweetalert2.all.js"></script>
    <script src="~/Scripts/modal.js"></script>
    <script src="~/Scripts/jquery.dataTables.min.js"></script>
    <script src="~/Scripts/Home/Index.js"></script>
    <script src="~/Scripts/jquery.tabletojson.min.js"></script>
    <script src="~/Scripts/jquery.jeditable.min.js"></script>
</body>
</html>

