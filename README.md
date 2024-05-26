# SI_2024_lab2_223205
# Втора лабараториска вежба по софтверско инжинерство
Ana Popeska, бр на индекс 223205
# CFG во документација:
![image](https://github.com/anapopeska/SI_2024_lab2_223205/assets/166449873/8bdc416d-bdb5-4ead-a86d-5331167e6767)

# Цикломатцка комплексност 
Цикломатската комплексност 𝑉(𝐺)
V(G) може да се пресмета со формулата:
V(G)=E−N+2P
каде E е бројот на ребра, N е бројот на јазли, и P е бројот на поврзани компоненти (обично 1 за една функција).

V=E-N+2P Е=48 Н=40 V=48-40+2 V=10

# Every Branch критериум (Test-Cases)
Тест-1: allItems = []
-Бидејќи allItems е null, ќе се фрли исклучок.

Тест-2: name = null, barcode = null
-Со креирање на Item, со name = null, на името ќе се додели вредност "unknown", а за barcode, тогаш ќе се фрли исклучок.

Тест-3: name = "Item", barcode = "123abc"
-Со креирање на Item, со name = "Item", и barcode = "123abc", за barcode ќе фрли исклучок бидејќи има недозволени знаци во самиот баркод.

Тест-4: name = "Item", barcode = "012345", discount = 0.5F, price = 400, payment = 200
-Со креирање на Item со name = "Item", barcode = "012345", discount = 0.5F, и price = 400, за сумата ќе се пресмета 400*0.5 = 200, па потоа од сумата ќе се одземе 30 и ќе добиеме 170 < 200, за кое ќе се врати true.

Тест-5: name = "Item", barcode = "012345", discount = 0, price = 100, payment = 50
-Со креирање на Item со name = "Item", barcode = "012345", discount = 0, и price = 100, за сумата ќе се доделе вредноста 100, бидејќи сумата не е помала од наплатата ќе се врати false.

# Multiple Condition критериум (Test-Cases)

-за условот: if(item.getPrice() > 300 && item.getDiscount() > 0 && item.getBarcode().charAt(0) == '0')

True|True|True: [item.getPrice() = 400; item.getDiscount() = 0.5F; item.getBarcode() = "012345"]
400 > 300 ќе врати точно, 0.5 > 0 ќе врати точно, '0' == '0' ќе врати точно

True|True|False: [item.getPrice() = 400; item.getDiscount() = 0.5F; item.getBarcode() = "123abc"
400 > 300 ќе врати точно, 0.5 > 0 ќе врати точно, '1' == '0' ќе врати неточно

True|False|X: item.getPrice() = 400; item.getDiscount() = 0; item.getBarcode() = "xxxxx"
400 > 300 ќе врати точно, 0 > 0 ќе врати неточно, бидејќи во if условот имаме "&&" или логичко "И", доколку еден од условите не е исполнет, останатите не се разгледуваат и нема да се проверат.

False|X|X: item.getPrice() = 250; item.getDiscount() = xxxxx; item.getBarcode() = "xxxxx"
250 > 300 ќе врати неточно, бидејќи во if условот имаме "&&" или логичко "И", доколку еден од условите не е исполнет, останатите не се разгледуваат и нема да се проверат.
