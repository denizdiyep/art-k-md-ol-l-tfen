class YatakOdasiToplama:
    def __init__(self):
        self.adimlar = [
            "Yatak örtüsünü düzelt.",
            "Yastıkları yerleştir.",
            "Yerdeki eşyaları topla.",
            "Dolabı düzenle.",
            "Odanı süpür.",
            "Pencereleri aç ve havalandır."
        ]

    def odadan_topla(self):
        print("Yatak odasını toplama işlemi başlatıldı!\n")
        
        for adim in self.adimlar:
            input(f"{adim} (Devam etmek için 'Enter' tuşuna basın...)")
        
        print("\nYatak odası toplama işlemi tamamlandı!")

# Yatak odası toplama işlemi başlatılır
toplayici = YatakOdasiToplama()
toplayici.odadan_topla()
