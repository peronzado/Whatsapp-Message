import time
import pyautogui
import webbrowser
from selenium import webdriver
from selenium.webdriver.common.keys import Keys
import pandas as pd
import numpy as np
import pyautogui
import keyboard

# Carregue a planilha Excel
df = pd.read_excel('resultados.xlsx')

# Substitua "Não encontrado" por NaN
df.replace("Não encontrado", np.nan, inplace=True)

# Remova as células com valores nulos
df.dropna(subset=['Telefone'], inplace=True)

# Selecione a coluna de telefone e remova os caracteres especiais
telefones = df['Telefone'].apply(lambda x: '55' + str(x).replace('(', '').replace(')', '').replace('-', '').replace(' ', ''))

# Salve a lista de números de telefone como uma variável Python
telefones = telefones.tolist()

# Define a mensagem a ser enviada
mensagem = # Enter the message you want to send to Whatsapp, between ''

bytes_mensagem = mensagem.encode('utf-8')
bytes_mensagem = bytes_mensagem.decode('utf-8')

# Inicia o driver do Chrome
driver = webdriver.Chrome()

# Abre o WhatsApp Web
driver.get('https://web.whatsapp.com/')

# Espera o usuário fazer o login manualmente
input('Faça o login manualmente no WhatsApp Web e aperte Enter para continuar...')

# Espera alguns segundos para garantir que a página carregou completamente
counter = 0
totalist = len(telefones)

# Para cada telefone na lista
for telefone in telefones:
    # Abre a conversa com o telefone
    time.sleep(5)
    counter += 1
    print("Iteration" + str(counter) + "of" + str(totalist))

    driver.get(f'https://web.whatsapp.com/send?phone={telefone}')

    time.sleep(5)

    pyautogui.click()

    time.sleep(5)

    pyautogui.click()

    time.sleep(5)

    # Digita a mensagem
    #pyautogui.typewrite(mensagem, encoding='utf-8')
    keyboard.write(bytes_mensagem)

    time.sleep(10)

    # Envia a mensagem pressionando as teclas de atalho
    pyautogui.hotkey('enter', 'enter')



    time.sleep(3)
