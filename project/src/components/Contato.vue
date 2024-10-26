<template>
    <div id="contato" class="flex">
        <div class="footer-logo-container">
            <div class="logo-container-footer">
                <img src="/images/logo.png" alt="AgráriaTEC Logo" />
            </div>
            <div class="description-footer">
                <p>
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin semper tortor.
                </p>
            </div>
        </div>
        <div id="rowSeparator"></div>
        <div id="containerContatos" class="green-color">
            <h4>informações de Contato:</h4>
            <p><i class="fa-brands fa-instagram"></i> agrariatec</p>
            <p><i class="fa-brands fa-facebook"></i> Agrária Tec </p>
            <p><i class="fa-solid fa-envelope"></i> agraricatec@example.com </p>
        </div>
    </div>
    <!-- <div id="footerColor"></div> -->
</template>

<style>
.footer-logo-container {
    flex: 1;
    padding: 20px;
}

.logo-container-footer img {
    max-width: 100%;
    height: auto;
}

.description-footer {
    margin-top: 10px;
}

#containerContatos {
    flex: 1;
    padding: 20px;
}

#rowSeparator {
    border-left: 1px solid #ccc;
    height: 100px;
    margin: 0 20px;
}

#footerColor {
    background-color: #f2f2f2;
    height: 60px;
}

@media (max-width: 768px) {
    .flex {
        flex-direction: column;
        align-items: center;
    }

    #rowSeparator {
        border: none;
        height: 0;
        margin: 10px 0;
    }

    .footer-logo-container,
    #containerContatos {
        text-align: center;       
    }
}
</style>