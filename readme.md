# Request
# ** Landing page for product **



## Source на ленд темплейта
	** https://theme-land.com/sapp/demo/index-2.html

## Реален продукт на който правим лендинг
	** https://geda.bg/bg/geda-lift-250-comfort_p989.html


## Задание
** Лендинг страница - за продукт
Изисквания към страницатаю
	- Всички кодове са само в 1 файл ( index.html ) - задължително е да е HTML за да може да се хоства на всякакви машини без да се изисква инсталация на каквото и да е.
	- Всички JS функции да се извикават след като се зареди страницата ( window.onload ) 
	- Има файл който се казва product.json - този файл симулира сървър. При деплойване на страницата няма да го има ще бъде заменен от реален път към подобен JSON урл ( fetch("./product.json") ) - за тестови цели го ползваме.
	- Продукт който трябва да бъде визуализиран на тази лендинг страница е : 
 

 ### Елементи на лендинг страницата 
	- Лого - идва от ( json протокола - респективно сървъра )
	- Име на продукта
	- Кратка информация
	- Главна снимка на продукта
	- Call to Action (CTA) - бутон - всички бутони или снимки като ги кликаш трабва да водят към - "buy_link"
	- Спецификация на продукта - прелистия я както сметнеш за добре
	- Пак Call to Action (CTA) бутон
	- Често задавани въпроси
	- Call to Action (CTA) бутон

Нищо друго не трабва да има на тази лендинг страница - Дори да сложиш бутон 

## SEO елементи
	- 1 бр. h1 - zaglawie
	- след него прараграф <р>
	- Следват всички H2, H3... не се повтарят H* тагове от всеки вид трабва да има само 1
	- Всички снимки трабва да имат ALT
	- Всички линкове трябват да имат title 
	- Всички og тагове
	- всички twitter тагове
	- Даеам примерен HTML код за микро дата
  
```
<div itemscope itemtype="https://schema.org/Product">
  <h1 itemprop="name">Примерен продукт</h1>
  
  <img src="example-product.jpg" alt="Примерен продукт" itemprop="image" />
  
  <div itemprop="offers" itemscope itemtype="https://schema.org/Offer">
    <span>Цена: </span>
    <span itemprop="priceCurrency" content="BGN">лв</span>
    <span itemprop="price" content="199.99">199.99</span>
    <link itemprop="availability" href="https://schema.org/InStock">Наличен</link>
  </div>
  
  <p itemprop="description">Това е описание на примерен продукт. Отличен за ежедневна употреба с високо качество.</p>

  <div itemprop="aggregateRating" itemscope itemtype="https://schema.org/AggregateRating">
    <span>Рейтинг: </span>
    <span itemprop="ratingValue">4.5</span> / 
    <span itemprop="reviewCount">25</span> отзива
  </div>

  <meta itemprop="sku" content="12345" />
  <meta itemprop="brand" content="BrandName" />
</div>
```
	- Ето пример за JSON-LD за продукт:
```
<script type="application/ld+json">
{
  "@context": "https://schema.org/",
  "@type": "Product",
  "name": "Примерен продукт",
  "image": "https://example.com/images/example-product.jpg",
  "description": "Това е описание на примерен продукт. Отличен за ежедневна употреба с високо качество.",
  "sku": "12345",
  "brand": {
    "@type": "Brand",
    "name": "BrandName"
  },
  "offers": {
    "@type": "Offer",
    "url": "https://example.com/product-page",
    "priceCurrency": "BGN",
    "price": "199.99",
    "priceValidUntil": "2024-12-31",
    "itemCondition": "https://schema.org/NewCondition",
    "availability": "https://schema.org/InStock",
    "seller": {
      "@type": "Organization",
      "name": "Примерен магазин"
    }
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.5",
    "reviewCount": "25"
  }
}
</script>
```
	- задължително ползване на ARIA таговете и указатели
```
<div itemscope itemtype="https://schema.org/Product" role="region" aria-labelledby="product-title">
  <h1 id="product-title" itemprop="name" aria-label="Примерен продукт">Примерен продукт</h1>
  
  <img src="example-product.jpg" alt="Примерен продукт за ежедневна употреба" itemprop="image" aria-describedby="img-desc"/>
  
  <p id="img-desc" role="note">Изображение на Примерен продукт</p>

  <div itemprop="offers" itemscope itemtype="https://schema.org/Offer" role="contentinfo">
    <span>Цена: </span>
    <span itemprop="priceCurrency" content="BGN" aria-label="Цена в български лев">лв</span>
    <span itemprop="price" content="199.99" aria-label="199.99 лева">199.99</span>
    <link itemprop="availability" href="https://schema.org/InStock" aria-label="Наличен">Наличен</link>
  </div>
  
  <p itemprop="description" aria-live="polite">Това е описание на примерен продукт. Отличен за ежедневна употреба с високо качество.</p>

  <button role="button" aria-pressed="false">Купи сега</button>
</div>
```
	- Да се използва Lazy Loading 
```
<img src="primeren-produkt.webp" alt="Примерен Продукт" loading="lazy" />
```
	- Задължително: ** Чист и валидиран HTML **
	- Прелистване на всички FAQ в HTML + shema : Пример за FAQ схема:
```
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Какви са основните предимства на Примерен Продукт?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Примерен Продукт е с високо качество и подходящ за ежедневна употреба."
      }
    },
    {
      "@type": "Question",
      "name": "Как мога да поръчам Примерен Продукт?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Можете да поръчате директно от нашия сайт, като натиснете бутона 'Купи сега'."
      }
    }
  ]
}
</script>
```

## Ако ти липсват полета в JSON документа си ги добави. Общо взето моделирай го така, че да отговаря на всички описани по-горе стандарти.

### Ако искаш можеш свободно да добавиш нещо което смяташ, че съм пропуснал.
Ако добавяш елементи или функционалности просто сложи коментари "защо" и тн.