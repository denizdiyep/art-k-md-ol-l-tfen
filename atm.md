class ATM:
    def __init__(self, pin, bakiye=0):
        self.pin = pin
        self.bakiye = bakiye

    def pin_dogrula(self, girilen_pin):
        return self.pin == girilen_pin

    def bakiye_goruntule(self):
        print(f"\nHesap Bakiyesi: {self.bakiye} TL")

    def para_yatir(self, miktar):
        if miktar > 0:
            self.bakiye += miktar
            print(f"{miktar} TL yatırıldı. Güncel bakiye: {self.bakiye} TL")
        else:
            print("Geçersiz miktar!")

    def para_cek(self, miktar):
        if miktar > 0 and miktar <= self.bakiye:
            self.bakiye -= miktar
            print(f"{miktar} TL çekildi. Güncel bakiye: {self.bakiye} TL")
        elif miktar > self.bakiye:
            print("Yetersiz bakiye!")
        else:
            print("Geçersiz miktar!")


# ATM simülasyonunu başlatalım
atm = ATM(pin=1234, bakiye=1000)

# Kullanıcının PIN'ini doğrula
girilen_pin = int(input("Lütfen PIN'inizi giriniz: "))

if atm.pin_dogrula(girilen_pin):
    print("\nPIN doğrulandı. Hoş geldiniz!")
    
    while True:
        print("\nLütfen bir işlem seçiniz:")
        print("1. Bakiye Görüntüle")
        print("2. Para Yatır")
        print("3. Para Çek")
        print("4. Çıkış")
        
        secim = int(input("Seçiminiz: "))

        if secim == 1:
            atm.bakiye_goruntule()
        elif secim == 2:
            miktar = float(input("Yatırılacak miktarı giriniz: "))
            atm.para_yatir(miktar)
        elif secim == 3:
            miktar = float(input("Çekilecek miktarı giriniz: "))
            atm.para_cek(miktar)
        elif secim == 4:
            print("Çıkış yapılıyor...")
            break
        else:
            print("Geçersiz seçim! Lütfen tekrar deneyin.")
else:
    print("PIN doğrulaması başarısız! Lütfen tekrar deneyiniz.")
