<!-- ABOUT THE PROJECT -->
## ebebek SAP Ödevi

1)	SAP ERP sistemine hangi uygulama ile erişim sağlanmaktadır?  
	SAP ERP sistemine erişmek için `Oracle VirtualBox veya VMWare Player` kullanılır. Bize verilen sanal makinedeki sunucuya bağlanıp IDES isimli SAR ERP ürünü kullanılır. Fiziksel olarak bir bakineye de kurulum yapılabilir.  
	
2)	SAP Editor ekranına hangi işlem kodu ile erişilmektedir?  
	`SE38` işlem kodu ile SAP editör ekranına erişim sağlanır.  
	
3)	Genel olarak bir değişken tanımlamak istediğinde, değişkenin isim standardı nasıl olmalıdır? Örnek verebilir misiniz?  
	Değişken tanımlama SAP içerisinde `data:` ile yapılır. Değişkkenler local ve global olmak üzere ikiye ayrılır.  
	```java
	data: gv_product type char50.  
	gv_product = 'Phone'.  
	```  
	
4)	Birden fazla değeri bir küme altında tutmak isterseniz hangi yapıyı kurmanız gerekir?  
	`Structure` ile birden fazla veri bir küme içerisinde tutulabilir. Bunun için de SAP üzerinde bir Structure oluşturmak gerekmektedir.  
	
5)	Structure ,data element , tablo gibi yapılar SAP de hangi işlem kodundan oluşturulmaktadır ?  
	Data Dictionary kısmından `SE11` ile erişim sağlanmaktadır.  
	
6)	Ekranda ürün kodu ve stok alanım parametre olarak bulunsun. Bu parametreler ile program içerisinde EB10000001, EB10000002, EB10000003, EB10000004, EB10000005, EB10000006, EB10000007 ürünleri internal tabloya ekleyip ardından parametreler ile filtre özelliğini kullanarak bir kod satırı yazar mısınız?  
	```java
	gt_product-urunkodu = ‘EB10000001’.
	gt_product-stok = ‘20’.
	append gt_product. 
	
	gt_product-urunkodu = ‘EB10000002’.
	gt_product-stok = ‘30’.
	append gt_product. 
	
	
	gt_product-urunkodu = ‘EB10000003’.
	gt_product-stok = ‘0’.
	append gt_product. 
	
	gt_product-urunkodu = ‘EB10000004’.
	gt_product-stok = ‘50’.
	append gt_product. 
	
	gt_product-urunkodu = ‘EB10000005’.
	gt_product-stok = ‘60’.
	append gt_product. 
	
	gt_product-urunkodu = ‘EB10000006’.
	gt_product-stok = ‘0’.
	append gt_product. 
	
	gt_product-urunkodu = ‘EB10000007’.
	gt_product-stok = ‘90’.
	append gt_product. 
	
	
	selection-screen begin of block part1 with frame title text-001.
	PARAMETERS: p_urunkd type ZSD_ST_PRODUCT-urunkodu.
	PARAMETERS: p_urunst type ZSD_ST_PRODUCT-stok.
	selection screen end of block part1.
	```

7)	Altıncı maddede yapılan çalışmalara ek olarak toplam ürün stoğunu görmemizi sağlayan bir kod satırı yazabilir misiniz?  
	```java
	data: gv_toplamstok type int2.
	gv_toplamstok = 0.
	
	loop at gt_product.
	gv_toplamstok = gv_toplamstok + gt_product-stok.
	endloop.
	
	WRITE:'Toplam Stok' , gv_toplamstok.
	```
	
8)	Stoğu sıfır olan ürünleri gösteren bir  rapor yazabilir misiniz ? (6. Maddedeki ürünlerin 2 tanesine stok olarak 0 değeri atayın.)  
	```java
	loop at gt_product.
	if gt_product-stok eq 0.
	WRITE:'Ürün Kodu' , gt_product-urunkodu , 'Stok Sayısı' , gt_product-stok.
	endif.
	endloop.
	```


<!-- CONTACT -->
## Contact

### Furkan Kirenci

<a href="https://github.com/furkankirenci" target="_blank">
<img  src=https://img.shields.io/badge/github-%2324292e.svg?&style=for-the-badge&logo=github&logoColor=white alt=github style="margin-bottom: 20px;" />
</a>
<a href="https://www.linkedin.com/in/furkan-kirenci-912668245/" target="_blank">
<img src=https://img.shields.io/badge/linkedin-%231E77B5.svg?&style=for-the-badge&logo=linkedin&logoColor=white alt=linkedin style="margin-bottom: 20px; margin-left:20px" />
</a>

<!-- PROJECT-BOOTCAMP-PRACTICUM PART -->
<br />

## ebebek Java & QA & SAP Spartacus Practicum
<div align="center">
  <a href="https://www.e-bebek.com">
    <img src="https://github.com/furkankirenci/ebebekFinalCase/blob/main/images/ebebek-logo.png" alt="Logo" width="200" height="50">
  </a>

<h3 align="center">Company: ebebek</h3>
</div>
<br>
<br><br>
<div align="center">
  <a href="https://www.patika.dev/tr">
    <img src="https://github.com/furkankirenci/ebebekFinalCase/blob/main/images/patika-logo.svg" alt="Logo" width="240" height="50">
  </a>
<h3 align="center">Organizer: Patika.dev</h3>
</div>
