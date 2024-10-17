class CopKutusu:
    def __init__(self, kapasite):
        self.kapasite = kapasite
        self.copler = []

    def cop_at(self, cop):
        if len(self.copler) < self.kapasite:
            self.copler.append(cop)
            print(f"{cop} çöpe atıldı.")
        else:
            print("Çöp kutusu dolu! Lütfen çöp kutusunu boşaltın.")

    def bosalt(self):
        if self.copler:
            print(f"Çöp kutusu boşaltıldı. {len(self.copler)} çöp atılmıştı.")
            self.copler = []
        else:
            print("Çöp kutusu zaten boş.")

    def doluluk_durumu(self):
        print(f"Çöp kutusunda {len(self.copler)} çöp var. Kapasite: {self.kapasite}")


# Çöp kutusu tanımlayalım
cop_kutusu = CopKutusu(3)  # Kapasite 3 çöp

# Çöpler atalım
cop_kutusu.cop_at("Muz kabuğu")
cop_kutusu.cop_at("Su şişesi")
cop_kutusu.cop_at("Kağıt parçası")

# Doluluk durumu kontrolü
print("\nDoluluk Durumu:")
cop_kutusu.doluluk_durumu()

# Bir çöp daha atmaya çalışalım
cop_kutusu.cop_at("Plastik poşet")

# Çöp kutusunu boşaltalım
cop_kutusu.bosalt()

# Güncel durumu kontrol edelim
print("\nGüncel Doluluk Durumu:")
cop_kutusu.doluluk_durumu()
