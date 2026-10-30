# Отчёт. День 5

По каждому заданию: что было не так и как ты это заметил. Одной-двумя фразами.

**Задание 1 (сайт без оформления): в указании названия файла была ошибка (styles а не style) из-за чего сайт не мог применить оформление**

**Задание 2 (цена undefined): price было написано с большой буквы из-за чего запрос не выполнялся правильно (price и Price для оператора разные)**

**Задание 3 (фильтр по категории): мы приравнивали текст и числа. благодаря Number мы превращали текст в числа**

**Задание 5 (второй пончик): мы прибавляли количество товара в корзине но оно не изменялось т.к не сохранялось. я присвоила количеству +1 (line.quantity += 1;)**

**Задание 6 (не тот крестик): метод требует оставить в корзине то чему равен Id. Нам нужно сделать наоборот поэтому === заменила на !==**

**Что было самым сложным:**

///



Задание 4



&#x20;       const searchText = searchInput.value;

&#x20;   if (searchText !== '') {

&#x20;       

&#x20;       products = products.filter(p => p.name.toLowerCase().includes(searchText.toLowerCase()));

&#x20;       

&#x20;       

&#x20;   }



&#x20;   renderProducts(products);

}



Задание 7



let total = 0;

for (const line of cart) {

&#x20;   total += line.price \* line.quantity;

}

totalText.textContent = `Итого: ${total} ₽`;



Задание 8



async function makeOrder() {

&#x20;   if (clientSelect.value === '') {

&#x20;       showMessage('Выбери клиента')

&#x20;       return;

&#x20;   }

&#x20;   if (cart.length === 0) {

&#x20;       showMessage('Корзина пуста')



&#x20;       return;



&#x20;   }

&#x20;   const result = await createOrder(clientSelect.value, cart);

&#x20;   if (result.error) {

&#x20;       showMessage(result.error)

&#x20;       return;

&#x20;   }



&#x20;   showMessage(`Заказ № ${result.order.id} оформлен`);

&#x20;   cart = \[]

&#x20;   renderCart();

&#x20;   await loadProducts();

}

