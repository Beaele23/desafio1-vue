<template>
    <body>
    <div id="app">
        <div class="contenedorForm">
            <form v-on:submit.prevent="emitirCi">
                <div>
                    <label for="run">Run: </label>
                    <input type="text" name="run" id="run" v-model="run"/>
                </div>

                <div>
                  <input type="submit" value="Emitir CI">
                </div>
            </form>
        </div>

        <!-- INICIO  -->
        <div class="carnet">
            <aside>
                <div>
                    <span>CEDULA DE INDENTIDAD</span>
                    <img
                        width="40"
                        src="./assets/img/chile_bandera.png"
                        alt=""
                    />
                </div>

                <img src="./assets/img/foto_elon.jpg" alt="" />
                <p>RUN {{run}}</p>
            </aside>

            <main>
                <header>
                    <p>REPUBLICA DE CHILE</p>
                    <span>SERVICIO DE REGISTRO CIVIL E IDENTIFICACIÓN</span>
                </header>
                <section>
                    <article>
                        <header>APELLIDOS</header>
                        <span>{{ apellidos }}</span>
                    </article>
                    <article>
                        <header>NOMBRES</header>
                        <span>{{nombres}}</span>
                    </article>

                    <div class="grid-2-colums">
                        <article>
                            <header>NACIONALIDAD</header>
                            <span>{{nacionalidad }}</span>
                        </article>
                        <article>
                            <header>SEXO</header>
                            <span>{{sexo}}</span>
                        </article>
                    </div>
                    <div class="grid-2-colums">
                        <article>
                            <header>FECHA DE NACIMIENTO</header>
                            <span>{{ fechaNacimiento }}</span>
                        </article>
                        <article>
                            <header>NÙMERO DOCUMENTO</header>
                            <span>{{numeroDocumento}}</span>
                        </article>
                    </div>
                    <div class="grid-2-colums">
                        <article>
                            <header>FECHA DE EMISIÒN</header>
                            <span>{{fechaEmision}}</span>
                        </article>
                        <article>
                            <header>FECHA DE VENCIMIENTO</header>
                            <span>{{fechaNacimiento}}</span>
                        </article>
                    </div>
                    <article>
                        <header>FIRMA DEL TITULAR</header>
                        <span>{{firmaTitular}}</span>
                    </article>
                </section>
            </main>
        </div>
        <!-- FIN -->
    </div>
</body>
</template>

<script>
export default {
    name: "App",
    components: {},
    data() {
        return {
            run: "5.555.555-5",
            apellidos: "Musk Peréz",
            nombres: "Elon Andrés",
            nacionalidad: "Colombia",
            sexo: "Masculino",
            fechaNacimiento: "22/11/1984",
            numeroDocumento: "00021132635",
            fechaEmision: "01/02/1986",
            fechaVencimiento: "01/02/2030",
            firmaTitular:"Elon Musk",
        };
    },
    methods:{
      emitirCi: function(){
        alert(`Cliente con run ${this.run} registrado con éxito.`);
      },
      
    }
};
</script>

<style scoped>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 60vh;
    font-size: 10px;
    font-family: sans-serif;
}

.contenedorForm {
    padding: 25px; 
}

.carnet {
    width: 400px;
    background: #c8deed;
    border-radius: 20px;
    display: grid;
    grid-template-columns: 30% 1fr;
    padding: 15px;
    box-shadow: 0px 0px 10px 2px black;
}

aside div {
    display: flex;
}

aside > img {
    margin-top: 15px;
    width: 100%;
    height: 60%;
}

aside p {
    text-align: center;
    font-size: 12px;
    font-weight: bold;
}

main {
    padding: 0px 14px;
}

main article {
    margin: 4px 0px;
}

main article header {
    font-weight: bold;
    color: #0235a4;
    font-size: 8px;
}

main header p {
    font-size: 20px;
    margin: 0;
    font-weight: bold;
    color: #0235a4;
}

main header span {
    font-size: 8px;
    color: #399be1;
}

main section {
    margin-top: 10px;
}

main section article span {
    font-size: 13px;
    font-weight: 600;
}

main section .grid-2-colums {
    display: grid;
    grid-template-columns: 50% 50%;
}
</style>
