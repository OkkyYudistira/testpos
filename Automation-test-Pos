from selenium import webdriver
from selenium.webdriver.common.by import By

class TestMainFormDemo:
    def __init__(self, file_path, title, client, description, app):
        self.file_path = file_path
        self.title = title
        self.client = client
        self.description = description
        self.app = app
        self.success = 0
        self.failed = 0
        self.driver = webdriver.Chrome()

    def run_test(self):
        try:
            self.driver.get("https://www.lambdatest.com/selenium-playground/simple-form-demo")

            # Message Test
            self.driver.find_element(By.ID, "user-message").send_keys("Halo Okky!")
            self.driver.find_element(By.ID, "showInput").click()
            result_msg = self.driver.find_element(By.ID, "message").text
            if result_msg == "Halo Okky!":
                self.success += 1
            else:
                self.failed += 1

            # Value Test
            self.driver.find_element(By.ID, "sum1").send_keys("10")
            self.driver.find_element(By.ID, "sum2").send_keys("5")
            self.driver.find_element(By.XPATH, "//button[text()='Get Total']").click()
            result_sum = self.driver.find_element(By.ID, "addmessage").text
            if result_sum == "15":
                self.success += 1
            else:
                self.failed += 1

        except Exception as e:
            print(f"Error during test: {e}")
            self.failed += 1
        finally:
            self.driver.quit()
            return self.success, self.failed
