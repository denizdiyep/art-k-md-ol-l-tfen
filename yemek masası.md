class Masa:
    def __init__(self, kisi_sayisi):
        self.kisi_sayisi = kisi_sayisi
        self.tabaklar = 0
        self.bardaklar = 0
        self.catal = 0
        self.kasik = 0

    def tabak_ekle(self, adet):
        if self.tabaklar + adet <= self.kisi_sayisi:
            self.tabaklar += adet
            print(f"{adet} tabak masaya eklendi.")
        else:
            print(f"Masada zaten yeterince tabak var! (Max: {self.kisi_sayisi})")

    def bardak_ekle(self, adet):
        if self.bardaklar + adet <= self.kisi_sayisi:
            self.bardaklar += adet
            print(f"{adet} bardak masaya eklendi.")
        else:
            print(f"Masada zaten yeterince bardak var! (Max: {self.kisi_sayisi})")

    def catal_ekle(self, adet):
        if self.catal + adet <= self.kisi_sayisi:
            self.catal += adet
            print(f"{adet} çatal masaya eklendi.")
        else:
            print(f"Masada zaten yeterince çatal var! (Max: {self.kisi_sayisi})")

    def kasik_ekle(self, adet):
        if self.kasik + adet <= self.kisi_sayisi:
            self.kasik += adet
            print(f"{adet} kaşık masaya eklendi.")
        else:
            print(f"Masada zaten yeterince kaşık var! (Max: {self.kisi_sayisi})")

    def masa_durumu(self):
        print(f"\nMasa Durumu:\n"
              f"{self.tabaklar} tabak\n"
              f"{self.bardaklar} bardak\n"
              f"{self.catal} çatal\n"
              f"{self.kasik} kaşık\n")


# Masa hazırlayalım
masa = Masa(4)  # 4 kişilik masa

# Masaya eşya ekleyelim
masa.tabak_ekle(4)
masa.bardak_ekle(4)
masa.catal_ekle(4)
masa.kasik_ekle(4)

# Masa durumu
print("\nMasa Hazırlandı:")
masa.masa_durumu()

# Fazladan eşya eklemeyi deneyelim
masa.tabak_ekle(1)  # Fazladan tabak eklemeye çalışıyoruz
masa.bardak_ekle(2)  # Fazladan bardak eklemeye çalışıyoruz
