import pyautogui
import pygetwindow as gw
import time

# Função para abrir o Google Chrome
def open_chrome():
    # Abre o menu iniciar (A tecla pode variar dependendo do sistema)
    pyautogui.hotkey('win', 's')
    time.sleep(1)  # Aguarda um pouco para o menu abrir
    pyautogui.typewrite('Chrome')  # Digita 'Chrome' na busca
    pyautogui.press('enter')  # Pressiona Enter para abrir o Chrome
    time.sleep(5)  # Aguarda o Chrome abrir

# Função para buscar Instagram e fazer login
def search_instagram_and_login():
    # Localiza a janela do Chrome
    chrome_window = gw.getWindowsWithTitle('Google Chrome')[0]
    chrome_window.activate()  # Ativa a janela do Chrome

    # Clica na barra de endereços do Chrome
    pyautogui.click(chrome_window.left + 300, chrome_window.top + 30)  # Ajuste a posição conforme necessário
    pyautogui.typewrite('instagram.com')  # Digita o endereço do Instagram
    pyautogui.press('enter')  # Pressiona Enter
    time.sleep(5)  # Aguarda o Instagram carregar

    # Ajuste as coordenadas conforme necessário
    # Primeiro, clique no campo de usuário
    pyautogui.click(600, 400)  # Clique no campo de usuário (ajuste as coordenadas conforme necessário)
    pyautogui.typewrite('seu_usuario')  # Digita o nome de usuário
    pyautogui.press('tab')  # Move para o campo de senha
    pyautogui.typewrite('sua_senha')  # Digita a senha
    pyautogui.press('enter')  # Pressiona Enter para fazer login

# Executa as funções
open_chrome()
search_instagram_and_login()
