# Dids
======

Santralinizde kullandığınız telefon numaraları hakkında bilgi alabileceğiniz adrestir.

## URL'ler
* `GET /dids.json` Santrale bağlı numaraları gösterir
* `GET /dids/:id.json` Numaraya ait detayları ve varsa mesai saatlerini gösterir

### Örnek Sonuç

*/dids?access_token=xxx*

```json
    {
       "dids":[
          {
             "id":1,
             "number":"900000000000",
             "state":"CONFIRMED",
             "destination":"10 - Auto attendant",
             "working_hour":true
          },
          {
             "id":2,
             "number":"900000000000",
             "state":"CONFIRMED",
             "destination":"101 - Group",
             "working_hour":true
          },
          {
             "id":3,
             "number":"900000000000",
             "state":"CONFIRMED",
             "destination":"1001 - Extension",
             "working_hour":false
          }
       ]
    }
```

### Detay Örnek Sonuç

*/dids/1?access_token=xxx*

```json
    {
       "did":{
          "id":1,
          "number":"900000000000",
          "state":"CONFIRMED",
          "destination":"10 - Auto attendant",
          "working_hour":true,
          "working_hours":{
             "monday":{
                "open":true,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             },
             "tuesday":{
                "open":true,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             },
             "wednesday":{
                "open":true,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             },
             "thursday":{
                "open":true,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             },
             "friday":{
                "open":true,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             },
             "saturday":{
                "open":true,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             },
             "sunday":{
                "open":false,
                "shift_start":"08:30",
                "shift_finish":"18:30"
             }
          }
       }
    }
```

### Sabitler

Dönen json içerisindeki bazı alanlarda bulunan değişken anlamları aşağıda verilmiştir.

* State
    * **DRAFT:** Taslak
    * **IN-PROGRESS:** İşleme alındı
    * **CONFIRMED:** Onaylandı
    * **CANCELED:** Vazgeçildi
    * **TERMINATED:** Kapatıldı
    * **NTS-DRAFT:** NTS ile taşıma taslak
    * **NTS-IN-PROGRESS:** NTS işleniyor
    * **NTS-CANCEL:** NTS vazgeçildi

* Destination
    * **Auto attendant:** Menü
    * **Group:** Grup
    * **Extension:** Dahili