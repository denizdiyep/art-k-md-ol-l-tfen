class ParkYeri:
    def __init__(self, numaralar):
        self.park_yerleri = {numara: None for numara in numaralar}

    def park_et(self, araba, numara):
        if self.park_yerleri[numara] is None:
            self.park_yerleri[numara] = araba
            print(f"{araba} {numara} numaralı yere park edildi.")
        else:
            print(f"{numara} numaralı park yeri dolu!")

    def park_cikar(self, numara):
        if self.park_yerleri[numara] is not None:
            araba = self.park_yerleri[numara]
            self.park_yerleri[numara] = None
            print(f"{araba} {numara} numaralı yerden çıkarıldı.")
        else:
            print(f"{numara} numaralı park yeri zaten boş!")

    def park_durumu(self):
        for numara, araba in self.park_yerleri.items():
            if araba is None:
                print(f"{numara} numaralı park yeri boş.")
            else:
                print(f"{numara} numaralı park yerinde {araba} var.")


# Arabaları ve park yerlerini tanımlayalım
park_yerleri = [1, 2, 3, 4, 5]  # 5 tane park yeri
park = ParkYeri(park_yerleri)

# Arabaları park et
park.park_et("Araba A", 1)
park.park_et("Araba B", 2)
park.park_et("Araba C", 3)

# Park durumu
print("\nPark Durumu:")
park.park_durumu()

# Arabayı çıkarmak
park.park_cikar(2)

# Güncel park durumu
print("\nGüncel Park Durumu:")
park.park_durumu()
