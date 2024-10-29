<template>
    <div id="contato" class="flex">
        <div class="footer-logo-container">
            <div class="logo-container-footer">
                <img src="/images/logo.png" alt="AgráriaTEC Logo" />
            </div>
            <div class="description-footer"> 
                <h4>Contatos Comerciais:</h4>
                <ul class="contact-list"> 
                    <li>
                        <i class="fa-solid fa-user"></i>
                        <span>Prof. Nilson Salvador: (35) 98858-3262</span>
                    </li>
                    <li>
                        <i class="fa-solid fa-user"></i>
                        <span>Rita Carvalho: (35) 98863-4592</span>
                    </li>
                    <li>
                        <i class="fa-solid fa-user"></i>
                        <span>Vanessa Mesquita: (35) 99157-6880</span>
                    </li>
                    <li>
                        <i class="fa-solid fa-user"></i>
                        <span>Igor Carvalho: (35) 99931-1346</span>
                    </li>
                </ul>
            </div>
        </div>
        <div id="rowSeparator"></div>
        <div id="containerContatos" class="green-color">
            <h4 class="tituloContatos">Informações de Contato:</h4>
            <p>
                <i class="fa-brands fa-instagram"></i>
                <a class="contact-link" :href="links.instagram" target="_blank"> agrariatec</a>
            </p>
            <p>
                <i class="fa-brands fa-facebook"></i>
                <a class="contact-link" :href="links.facebook" target="_blank">Agrária Tec</a>
            </p>
            <p>
                <i class="fa-solid fa-envelope"></i>
                <span>E-mail: <a class="contact-link"
                        :href="'mailto:agrariatec@trezcomunicacao.com'">agrariatec@trezcomunicacao.com</a></span>
            </p>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            links: {
                instagram: 'https://www.instagram.com/agrariatec/',
                facebook: 'https://www.facebook.com/p/Agr%C3%A1ria-Tec-61561230092492',
            }
        };
    }
};
</script>

<style>
.tituloContatos{
    text-align: center;
}

#contato {
    margin-bottom: 8px;
}

.contact-list {
    list-style: none;
    padding: 0;
    margin: 10px 0;
}

.contact-list li {
    display: flex;
    align-items: center;
    margin-bottom: 8px;
    padding: 5px;
    border-bottom: 1px solid #e0e0e0;
}

.contact-list li i {
    margin-right: 8px;
    color: #4CAF50;
    font-size: 1.2em;
}

.contact-link {
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

.footer-logo-container,
#containerContatos {
    display: flex;
    flex-direction: column;
    flex: 1;
    padding: 20px;
    box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
    background-color: #f9f9f9;    
}

#containerContatos {
    flex-direction: column;
}


.logo-container-footer img {
    max-width: 80%;
    height: auto;
    display: block;
    margin: 0 auto;
}

.description-footer h4,
#containerContatos h4 {
    color: #2E7D32;
    font-weight: bold;
    margin-bottom: 15px;
    font-size: 2em;
}

#rowSeparator {
    border-left: 2px solid #4CAF50;
    height: 100px;
    margin: 0 20px;
}

.logo-container-footer img {
    max-width: 50%; 
    height: auto;
    display: block;
    margin: 0 auto;
}

@media (max-width: 768px) {
    .flex {
        flex-direction: column;
    }

    .footer-logo-container,
    #containerContatos {
        width: 100%;
        padding: 10px;
        margin-bottom: 20px;
        align-items: stretch;
        /* Alinha os cards com o mesmo tamanho */
    }

    #rowSeparator {
        display: none;
    }

    .contact-list li i {
        font-size: 1em;
    }

    .contact-link {
        font-size: 16px;
    }
}

@media (max-width: 600px) {
    .contact-link {
        font-size: 14px;
    }

    .contact-link:hover {
        font-size: 1.05em;
    }

    .logo-container-footer img {
        max-width: 60%;
    }

    h4 {
        font-size: 1.2em;
    }
}
</style>
