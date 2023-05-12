# 1220505060 2.soru

 #include <stdio.h>

int binarySearch(int arr[], int low, int high, int x) {//aranan öğeyi ve sıralı diziyi (array) parametresi olarak alır.
    if (high >= low) {//Fonksiyon, arama yapılacak yarı dizi boyutu 1 olana kadar veya aranan öğe bulunana kadar tekrar eden bir süre içinde çalışır.
        int mid = low + (high - low) / 2;//Her dizin, dizin içindeki öğe bulunur ve aranan öğe ile karşılaştırılır.

        if (arr[mid] == x)
            return mid;

        if (arr[mid] > x)
            return binarySearch(arr, low, mid - 1, x);//Eğer ortadaki öğe aranan öğeden küçükse, arama yapılacak yarı dizi sağ taraf alınır.


        return binarySearch(arr, mid + 1, high, x);//Eğer ortadaki öğe aranan öğeden büyük ise, arama yapılacak yarı dizi sol yarısı alınır.
    }

    return -1;//Bu işlem, aranan öğe bulunana kadar veya arama yapılacak yarı dizi boyutu 1 olana kadar tekrar eder.Eğer aranan öğe bulunamazsa, -1 değeri döndürülür.
}

int main() {
    int dizi[]={4,8,3,84,47,76,9,24,68};
    int n = sizeof(dizi) / sizeof(dizi[0]);
    int x = 76;
    int sonuc = binarySearch(dizi, 0, n - 1, x);
    if (sonuc == -1) {
        printf("Eleman bulunamadi.");
    } else {
        printf("Eleman %d. indekste bulundu.", sonuc);
    }
    return 0;
}
