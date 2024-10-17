class Siparis:
    def __init__(self):
        self.menu = {
            "Pizza": 50,
            "Hamburger": 35,
            "Salata": 20,
            "Suşi": 60,
            "Tavuk Döner": 25
        }
        self.siparisler = {}
        self.toplam_fiyat = 0

    def menu_goster(self):
        print("\nMenü:")
        for yemek, fiyat in self.menu.items():
            print(f"{yemek}: {fiyat} TL")

    def siparis_ver(self, yemek, adet):
        if yemek in self.menu:
            if yemek in self.siparisler:
                self.siparisler[yemek] += adet
            else:
                self.siparisler[yemek] = adet
            self.toplam_fiyat += self.menu[yemek] * adet
            print(f"{adet} adet {yemek} sipariş edildi.")
        else:
            print(f"{yemek} menüde bulunmuyor!")

    def siparis_durumu(self):
        print("\nSipariş Durumu:")
        if self.siparisler:
            for yemek, adet in self.siparisler.items():
                print(f"{adet} adet {yemek}")
            print(f"\nToplam Fiyat: {self.toplam_fiyat} TL")
        else:
            print("Henüz sipariş verilmedi.")

    def siparis_iptal(self, yemek):
        if yemek in self.siparisler:
            adet = self.siparisler.pop(yemek)
            self.toplam_fiyat -= self.menu[yemek] * adet
            print(f"{adet} adet {yemek} siparişi iptal edildi.")
        else:
            print(f"{yemek} siparişinizde bulunmuyor.")


# Sipariş işlemi başlat
siparis = Siparis()

# Menü göster
siparis.menu_goster()

# Siparişler verelim
siparis.siparis_ver("Pizza", 2)
siparis.siparis_ver("Suşi", 1)

# Sipariş durumu kontrol edelim
print("\nGüncel Sipariş Durumu:")
siparis.siparis_durumu()

# Siparişi iptal edelim
siparis.siparis_iptal("Pizza")

# Son durumu kontrol edelim
print("\nSon Sipariş Durumu:")
siparis.siparis_durumu()
