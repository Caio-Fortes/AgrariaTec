<template>
    <section id="contato">
        <div class="flex-container">
            <div class="footer-logo-container">
                <div class="logo-container-footer">
                    <img src="/images/logo.png" alt="AgráriaTEC Logo" />
                </div>
                <div class="description-footer">
                    <p>
                        Todos os direitos deste projeto são reservados a Trez Comunicação.<br />
                        Marco Cesar Xavier - ME, de acordo com a lei 9.610 de 19 de fevereiro de 1998.
                    </p>
                </div>
            </div>
            <div id="rowSeparator"></div>
            <div id="containerContatos">
                <h4 class="green-color">informações de Contato:</h4>
                <div class="contatos">
                    <ul class="contatos-digitais">
                        <li class="contato-item">
                            <i class="fa-brands fa-instagram"></i>
                            <a class="contact-link" :href="links.instagram" target="_blank"> agráriatec</a>
                        </li>
                        <li class="contato-item">
                            <i class="fa-brands fa-facebook"></i>
                            <a class="contact-link" :href="links.facebook" target="_blank">Agrária Tec</a>
                        </li>
                        <li class="contato-item">
                            <i class="fa-solid fa-envelope"></i>
                            <a class="contact-link email-link" :href="'mailto:' + links.email"> {{ links.email }}</a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data() {
        return {
            links: {
                instagram: 'https://www.instagram.com/agrariatec/',
                facebook: 'https://www.facebook.com/p/Agr%C3%A1ria-Tec-61561230092492',
                email: 'agrariatec@trezcomunicacao.com'
            }
        };
    }
};
</script>

<style>
/* mobile */
@media (max-width: 900px) {
    .flex-container {
        display: flex;
        margin: 10px;
        flex-direction: column;
    }

    .footer-logo-container {
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    #containerContatos {
        text-align: center;
    }

    #rowSeparator {
        display: none;
    }

    .contatos-digitais {
        flex: 1;
        display: flex;
        flex-direction: column;
        list-style-type: none;
        padding: 0;
        gap: 0.5rem;
        align-items: center;
    }
}

/* desktop */
@media (min-width: 900px) {
    .flex-container {
        display: flex;
        align-items: center;
        flex-wrap: nowrap;
        justify-content: flex-start;
    }

    .footer-logo-container {
        padding: 20px;
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    #rowSeparator {
        border-left: 1px solid #ccc;
        height: 100px;
        margin: 0px 2rem;
    }

    .contatos-digitais {
        flex: 1;
        display: flex;
        flex-direction: column;
        list-style-type: none;
        padding: 0;
        gap: 0.5rem;
    }
}

.contatos {
    display: flex;
    justify-content: space-between;
    width: 100%;
}

.logo-container-footer {
    max-width: 35vw;
}

.contato-item {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-family: "regular-InriaSans";
}

.contact-link {
    font-family: "bold-InriaSans";
    font-size: 18px;
    margin-left: 8px;
    color: #4CAF50;
    text-decoration: none;
    transition: color 0.3s ease, font-size 0.3s;
}

.contact-link:hover {
    color: #2E7D32;
}
</style>