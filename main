import pyautogui
import keyboard
import time
from selenium import webdriver
chrome_driver_path = "C:\development\chromedriver.exe"
driver = webdriver.Chrome(executable_path=chrome_driver_path)
url = "https://10fastfingers.com/typing-test/english"
driver.get(url)
time.sleep(5)
cookies = driver.find_element_by_xpath('//*[@id="CybotCookiebotDialogBodyLevelButtonLevelOptinAllowAll"]')
cookies.click()
input_tag = driver.find_element_by_xpath('//*[@id="inputfield"]')
input_tag.click()
index = 1
def main():
    for i in range(1):
        global index
        text_list = []
        for i in range(25):
            word = driver.find_element_by_xpath(f'//*[@id="row1"]/span[{index}]').text
            if word != "":
                text_list.append(word)
                index += 1
        print(text_list)
        for word in text_list:
            keyboard.press("space")
            keyboard.release("space")
            for char in word:
                time.sleep(0.05)
                if char == " ":
                    keyboard.press("space")
                    keyboard.release("space")
                else:
                    if char.istitle():
                        keyboard.press(char.title())
                        keyboard.release(char.title())
                    else:
                        keyboard.press(char)
                        keyboard.release(char)
        time.sleep(0.5)
        main()

main()

