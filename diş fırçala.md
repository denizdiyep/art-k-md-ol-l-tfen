import time

class DisFircalama:
    def __init__(self, sure=120):  # 120 saniye (2 dakika) fırçalama süresi
        self.sure = sure

    def fircala(self):
        print("Diş fırçalama başladı!")
        for kalan_sure in range(self.sure, 0, -10):  # Her 10 saniyede bir bilgi verilir
            print(f"{kalan_sure} saniye kaldı.")
            time.sleep(10)  # 10 saniye bekle
        print("Diş fırçalama tamamlandı! Ağzınızı durulayabilirsiniz.")

# Diş fırçalama işlemi başlatılır
dis_fircalama = DisFircalama()
dis_fircalama.fircala()
