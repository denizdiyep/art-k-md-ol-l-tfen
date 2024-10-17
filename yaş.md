from datetime import datetime

class YasHesaplama:
    def __init__(self):
        self.dogum_tarihi = None

    def dogum_tarihini_al(self):
        tarih_str = input("Doğum tarihinizi girin (GG-AA-YYYY formatında): ")
        try:
            self.dogum_tarihi = datetime.strptime(tarih_str, "%d-%m-%Y")
        except ValueError:
            print("Geçersiz tarih formatı! Lütfen GG-AA-YYYY formatında girin.")

    def yas_hesapla(self):
        if self.dogum_tarihi is None:
            print("Önce doğum tarihinizi girmelisiniz!")
            return
        
        bugun = datetime.now()
        yas = bugun.year - self.dogum_tarihi.year

        # Doğum günü geçmedi ise yaş bir eksik
        if (bugun.month, bugun.day) < (self.dogum_tarihi.month, self.dogum_tarihi.day):
            yas -= 1

        print(f"Yaşınız: {yas} yıl")

# Yaş hesaplama işlemi
yas_hesaplayici = YasHesaplama()

# Doğum tarihini al
yas_hesaplayici.dogum_tarihini_al()

# Yaş hesapla
yas_hesaplayici.yas_hesapla()
