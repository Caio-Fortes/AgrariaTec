<template>
    <section id="programacao">
        <div id="containerProgramacao">
            <div class="set-grid">
                <div id="textCenter">
                    <h4 class="green-color" style="margin-bottom: 0px;">
                        Atrações do Evento
                    </h4>
                    <h1>O que vou encontrar?</h1>
                </div>
                <div class="column-3">
                    <img src="/images/home.png" id="imgCeleiro"/>
                </div>
            </div>
            <div class="set-flex">
                <div class="column-1 cards">
                    <div class="image-cards">
                        <img src="/images/icons/trator.png" />
                    </div>
                    <div class="titles-container">
                        <div class="title-cards">Tecnologias e Inovações</div>
                        <p> Apresentação de novas tecnologias </p>
                        <p> Exposição de máquinas e equipamentos</p>
                        <p> Soluções para irrigação </p>
                        <p> Energia fotovoltaica</p>
                    </div>
                </div>
                <div class="column-1 cards">
                    <div class="image-cards">
                        <img src="/images/icons/frutos.png" />
                    </div>
                    <div class="titles-container">
                        <div class="title-cards">Produtos e Insumos</div>
                        <p> Fertilizantes </p>
                        <p> Defensivos</p>
                        <p> Ração </p>
                        <p> Produtos veterinários</p>
                        <p> Sementes</p>
                    </div>
                </div>
                <div class="column-1 cards">
                    <div class="image-cards">
                        <img src="/images/icons/vaca.png"/>
                    </div>
                    <div class="titles-container">
                        <div class="title-cards">Interação e Participação</div>
                        <p> Instituições financeiras </p>
                        <p> Espaço à agricultura familiar </p>
                        <p> Autoridades ligadas ao agronegócio </p>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<style scoped>
* {
    box-sizing: border-box;
}

body {
    margin: 0;
    overflow-x: hidden;
}

.set-grid {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    gap: 20px;
    max-width: 100vw;
}

#imgCeleiro {
    max-height: 14vw;
}

.column-3 {
    justify-self: end;
}

.set-flex {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    max-width: 100vw;
}

.cards {
    flex: 1 1 calc(33.33% - 20px);
    min-width: 300px;
    margin: 0;
    box-sizing: border-box;
    align-items: center;
}

@media (max-width: 1090px) {
    .cards {
        flex: 1 1 calc(50% - 20px);
        align-items: center;

    }

    .column-1.cards:nth-child(3) {
        flex-basis: 100%;
        margin: 0 auto 10px;
        max-width: 100%;
        align-items: center;
    }

}

@media (max-width: 768px) {
    .set-flex {
        flex-direction: column;
        align-items: center;
    }

    .cards {
        width: 100%;
        max-width: 100%;
        margin-bottom: 20px;
        flex-basis: auto;
        align-items: center;
    }

    .column-3 img {
        width: 100%;
        max-width: 300px;
        margin: 0 auto;
    }

    @media (max-width: 480px) {
        .column-3 img {
            max-width: 250px;
        }

    }
}

@media (max-width: 400px) {
    .cards {
        padding: 10px;
        text-align: center;
        overflow: hidden;
        height: auto;
        align-items: center;
    }

    .titles-container {
        font-size: 14px;
    }
}

@media (max-width: 375px) {
    .cards {
        padding: 5px;
        text-align: center;
        overflow: hidden;
        height: auto;
        font-size: 12px;
        align-items: center;
    }

    .titles-container {
        font-size: 14px;

        .image-cards img {
            max-width: 100%;
            height: auto;
        }

        p {
            margin: 0;
        }
    }
}
</style>
