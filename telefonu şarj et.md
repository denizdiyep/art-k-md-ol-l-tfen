import time

class TelefonSarjEtme:
    def __init__(self, sarj_sure=60):  # Şarj süresi 60 saniye
        self.sarj_sure = sarj_sure
        self.sarj_durumu = 0  # Başlangıçta şarj durumu 0%

    def sarj_et(self):
        print("Telefon şarj etmeye başladı!")
        for i in range(0, self.sarj_sure + 1, 10):  # Her 10 saniyede bir güncelleme
            self.sarj_durumu = i
            print(f"Şarj durumu: {self.sarj_durumu}%")
            time.sleep(10)  # 10 saniye bekle
        self.sarj_durumu = 100
        print("Telefon tamamen şarj oldu!")

# Telefon şarj etme işlemi başlatılır
telefon = TelefonSarjEtme()
telefon.sarj_et()

