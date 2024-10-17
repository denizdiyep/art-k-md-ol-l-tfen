class NotHesaplama:
    def __init__(self):
        self.notlar = []

    def not_ekle(self, ders, notu):
        self.notlar.append((ders, notu))
        print(f"{ders} dersine {notu} eklendi.")

    def notlari_goster(self):
        if not self.notlar:
            print("Henüz not girilmedi.")
        else:
            print("\nGirilen Notlar:")
            for ders, notu in self.notlar:
                print(f"{ders}: {notu}")

    def ortalama_hesapla(self):
        if not self.notlar:
            print("Henüz not girilmedi, ortalama hesaplanamıyor.")
            return
        toplam = sum(notu for ders, notu in self.notlar)
        ortalama = toplam / len(self.notlar)
        print(f"\nNot Ortalaması: {ortalama:.2f}")
        if ortalama >= 60:
            print("Geçti!")
        else:
            print("Kaldı!")

# Not hesaplama işlemi
hesaplayici = NotHesaplama()

# Not ekleyelim
hesaplayici.not_ekle("Matematik", 75)
hesaplayici.not_ekle("Fizik", 50)
hesaplayici.not_ekle("Kimya", 65)

# Girilen notları gösterelim
hesaplayici.notlari_goster()

# Ortalama hesaplayalım
hesaplayici.ortalama_hesapla()
