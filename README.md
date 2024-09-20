# Automatizando testes com Robot Framework no padrão BDD
>
>
> <img width="486" alt="app sorteio - git" src="https://github.com/user-attachments/assets/610da83e-608b-4c1a-8ed0-53239cc3a338">
>
>
### Primeiro teste utilizando keywords da Selenium Library para interagir com os campos do formulário do organo e, assim, criar um card para uma colaboradora da empresa.

> ``` *** Settings ***
> Library    SeleniumLibrary
>
> *** Test Cases ***
> Abrir navegador e acessar o site organo
>    Open Browser    url=http://localhost:3000/    browser=Chrome
>
> Preencher os campos do formulário
> 
>    Input Text    id:from-nome     Angelica
>    Input Text    id:from-cargo    Engenharia de Automação
>    Input Text    id:from-image    https://picsum.photos/200/300
>    Click Element    class:lista-suspensa
>    Click Element    //option[contains(.,'Programação')]
>    Sleep    10s
> 
>    Click Element    form-botao
>    Element Should Be Visible    class:colaborador
>    Sleep    5s 
>
