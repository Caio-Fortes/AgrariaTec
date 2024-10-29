<template>
    <div class="footer-container">
        <div class="footer-logo-container">
            <div class="logo-container-footer">
                <img src="/images/logo.png" alt="AgráriaTEC Logo" />
            </div>
            <div class="description-footer">
                <p class="descricao-footer">
                    Todos os direitos deste projeto são reservados a Trez Comunicação. Marco Cesar Xavier - ME, de
                    acordo com a lei 9.610 de 19 de fevereiro de 1998.
                </p>
            </div>
        </div>

        <div id="containerContatos" class="green-color">
            <h4>Informações de Contato:</h4>

            <div class="contatos">
                <!-- Mídias Sociais -->
                <ul class="contatos-digitais">
                    <li class="contato-item">
                        <i class="fa-brands fa-instagram"></i>
                        <a class="contact-link" :href="links.instagram" target="_blank"> agrariatec</a>
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

                <!-- Telefones -->
                <ul class="telefones">
                    <li class="contato-item">
                        <i class="fa-solid fa-user"></i> Prof. Nilson Salvador: (35) 98858-3262
                    </li>
                    <li class="contato-item">
                        <i class="fa-solid fa-user"></i> Rita Carvalho: (35) 98863-4592
                    </li>
                    <li class="contato-item">
                        <i class="fa-solid fa-user"></i> Vanessa Mesquita: (35) 99157-6880
                    </li>
                    <li class="contato-item">
                        <i class="fa-solid fa-user"></i> Igor Carvalho: (35) 99931-1346
                    </li>
                </ul>
            </div>
        </div>
    </div>
    <div id="footerColor"></div>
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

<style scoped>
span {
    margin: 5px;
}

.descricao-footer {
    text-align: center;
    font-family: "bold-InriaSans";
    font-size: 1.2rem;
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
    font-size: 1.1em;
}

.email-link {
    word-break: break-all;
    white-space: normal;
}

.footer-container {
    display: flex;
}

.footer-logo-container,
#containerContatos {
    flex: 1;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    min-width: 50%;
    margin-left: 5px;
}

.logo-container-footer {
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
}

img {
    max-width: 50%;
}

#containerContatos {
    display: flex;
    flex-direction: column;
    margin-left: 20px;
}

.contatos {
    display: flex;
    justify-content: space-between;
    width: 100%;
}

.contatos-digitais,
.telefones {
    flex: 1;
    display: flex;
    flex-direction: column;
    list-style-type: none;
    padding: 0;
    gap: 0.5rem;
}

.contato-item {
    display: flex;
    align-items: center;
    gap: 0.5rem;
    font-family: "regular-InriaSans";
}

.logo-container-footer img {
    max-width: 50%;
}

@media (max-width: 768px) {
    .footer-container {
        display: flex;
        flex-direction: column;
        align-items: center; /* Centraliza o conteúdo horizontalmente */
        padding: 10px;       
    }

    .footer-logo-container,
    #containerContatos {
        min-width: 100%; 
        align-items: center; 
        text-align: center; 
    }

    .descricao-footer {
        font-size: 1.1rem;
        margin-bottom: 10px; 
    }

    .contact-link {
        font-size: 0.9rem;
    }

    .contatos {
        flex-direction: column; 
        align-items: center; 
        width: 100%;
        margin-top: -25px;
    }

    .contatos-digitais,
    .telefones {
        align-items: center; 
    }

    .logo-container-footer img {
        max-width: 70%;
    }
}

@media (max-width: 480px) {
    .descricao-footer {
        font-size: 1rem;
    }

    .contact-link {
        font-size: 0.8rem;
    }

    .logo-container-footer img {
        max-width: 90%;
    }
}
</style>
