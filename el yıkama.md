import time

class ElYikama:
    def __init__(self, sure=20):  # 20 saniyelik el yıkama süresi
        self.sure = sure

    def yikama_adimlari(self):
        print("1. Ellerinizi suyla ıslatın.")
        time.sleep(3)
        print("2. Sabun alın ve ellerinizi iyice köpürtün.")
        time.sleep(5)
        print("3. Ellerinizin her yerini (avucunuzu, parmaklarınızın arasını, tırnaklarınızın altını) ovalayın.")
        time.sleep(7)
        print("4. Ellerinizi suyla durulayın.")
        time.sleep(3)
        print("5. Ellerinizi temiz bir havluyla veya kurutucu ile kurulayın.")
        time.sleep(2)

    def yikama(self):
        print("El yıkama başladı!")
        self.yikama_adimlari()
        print(f"El yıkama tamamlandı! Toplam süre: {self.sure} saniye.")

# El yıkama işlemi başlatılır
el_yikama = ElYikama()
el_yikama.yikama()
