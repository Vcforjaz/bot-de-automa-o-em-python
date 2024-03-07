<h1><a href="https://vcforjaz.github.io/Meus-Projetos/"><img align="center" width="40px" src="https://vcforjaz.github.io/Meus-Projetos/favicon.ico"></a><a href="https://vcforjaz.github.io/Meus-Projetos/"><span> Site de portfólios hospedado no Git Pages.</span></a></h1>

# Bot de automacao em Python :
> [!TIP]
> Bot de automação de cadastro de produtos feito em Python, pode ser utilizado para ter como base na criação de outro bot, ou ediçao do mesmo para atender a sua maneira. 
Como dito anteriormente, o bot foi escrito em Python e utiliza duas bibliotecas. 
Biblioteca nativa 'time' e a Biblioteca adicional de automação 'pyautogui'.

# Visualize o código sem baixar :
#1. Entrar no sistema
import pyautogui        
import time

pyautogui.PAUSE=1.5
link = "https://dlp.hashtagtreinamentos.com/python/intensivao/login"
email = "teste@teste.com"
pw = "1234"

pyautogui.press("win")
pyautogui.write("Chrome")
pyautogui.press("enter")
pyautogui.press("tab")
pyautogui.press("tab")
pyautogui.press("tab")
pyautogui.press("tab")
pyautogui.press("Enter")
pyautogui.click(x=606, y=78)
pyautogui.hotkey("ctrl", "a")
pyautogui.write(link)
pyautogui.press("Enter")
time.sleep(3)

#2. Login
pyautogui.click(x=769, y=505)
pyautogui.write(email)
pyautogui.press("tab")
pyautogui.write(pw)
pyautogui.press("tab")
pyautogui.press("Enter")
time.sleep(3)

#3. Importar DB
import pandas
tabela = pandas.read_csv("produtos.csv")
print(tabela)

#4. Cadastrar produto/ação
for linha in tabela.index:

    codigo = tabela.loc[linha, "codigo"]
    marca = tabela.loc[linha, "marca"]
    tipo = tabela.loc[linha, "tipo"]
    categoria = tabela.loc[linha, "categoria"]
    preco = tabela.loc[linha, "preco_unitario"]
    custo = tabela.loc[linha, "custo"]
    obs = tabela.loc[linha, "obs"]
    
    pyautogui.click(x=737, y=354)

    pyautogui.write(codigo)
    pyautogui.press("tab")

    pyautogui.write(marca)
    pyautogui.press("tab")

    pyautogui.write(tipo)
    pyautogui.press("tab")

    pyautogui.write(str(tabela.loc[linha, "categoria"]))
    pyautogui.press("tab")

    pyautogui.write(str(tabela.loc[linha, "preco_unitario"]))
    pyautogui.press("tab")

    pyautogui.write(str(tabela.loc[linha, "custo"]))
    pyautogui.press("tab")

    if not pandas.isna(obs):
        pyautogui.write(obs)
    pyautogui.press("tab")

    pyautogui.press("enter")
    #5. Repeat process.
    pyautogui.click(x=184, y=385)
    pyautogui.scroll(1200)
#Victor Forjaz

## Link para download:
https://vcforjaz.github.io/Meus-Projetos/bot-python.py
