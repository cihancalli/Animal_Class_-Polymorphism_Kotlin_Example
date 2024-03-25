# Animal_Class_Polymorphism_Kotlin_Example

## Kotlin Uygulamasında Polymorphism Kullanarak Bir Sınıf Örneği Oluşturma

Polymorphism, birden fazla veri türünü veya davranışı tek bir arayüzde temsil etme yeteneğidir. Kotlin'de polymorphism, iki temel yöntemle kullanılabilir:

1. Kalıtım: Bir sınıf, başka bir sınıftan miras alarak onun özelliklerini ve davranışlarını devralabilir.

2. Arayüzler: Bir sınıf, bir veya birden fazla arayüzü uygulayarak belirli bir işlevsellik sözleşmesi sunabilir.

```bash
open class Hayvan(val isim: String) {
    open fun sesCikar() {
        println("Hayvan sesi.")
    }
}

class Kedi(isim: String) : Hayvan(isim) {
    override fun sesCikar() {
        println("Miyav.")
    }
}

class Kopek(isim: String) : Hayvan(isim) {
    override fun sesCikar() {
        println("Hav hav.")
    }
}

fun main() {
    val hayvanListesi: List<Hayvan> = listOf(Kedi("Mırmır"), Kopek("Karamel"))

    hayvanListesi.forEach { hayvan ->
        println(hayvan.isim)
        hayvan.sesCikar()
    }
}

```

```bash
Mırmır
Miyav.
Karamel
Hav hav.
```

Açıklama:

* Hayvan sınıfı, isim adında bir özelliğe ve sesCikar adında bir işlevselliğe sahip bir temel sınıf olarak tanımlanır.
* Kedi ve Kopek sınıfları, Hayvan sınıfından miras alarak onun özelliklerini ve davranışlarını devralır.
* sesCikar işlevi, her alt sınıfta farklı bir şekilde uygulanarak kediler için "miyav" ve köpekler için "hav hav" sesini üretir.
* main fonksiyonunda, Kedi ve Kopek nesnelerinden oluşan bir liste oluşturulur.
* Listedeki her nesne için, isim özelliği ve sesCikar işlevi sırasıyla yazdırılır.

Polymorphism'in Avantajları:

* Kod tekrarını azaltır.
* Kodun daha esnek ve modüler olmasını sağlar.
* Farklı türdeki nesneleri tek bir şekilde işlemeye olanak tanır.

Polymorphism'in Dezavantajları:

* Karmaşıklığı artırabilir.
* Hatalara yol açabilir.

Polymorphism'i Kullanırken Dikkat Edilmesi Gerekenler:

* Sınıf hiyerarşisini dikkatli bir şekilde tasarlamak gerekir.
* Her alt sınıfın, soyut sınıfta tanımlanan tüm işlevleri uygulaması gerekir.
* Kodun okunabilirliği ve anlaşılırlığı için açık ve net isimler kullanmak önemlidir.
