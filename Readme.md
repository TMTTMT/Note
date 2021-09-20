# LinQ

LinQ thì giống sql bình thường thì thay vì nó query để lấy dữ liệu trên sql server thì 
nó giúp mình xử lý dữ liệu ở backend.

VD: mình lấy ví dụ trên website cho dễ
Sau đâu là 1 tập dữ liệu products

```c#
`var products = new List<Product>()`
`{`
    `new Product(1, "Bàn trà",    400, new string[] {"Xám", "Xanh"},         2),`
    `new Product(2, "Tranh treo", 400, new string[] {"Vàng", "Xanh"},        1),`
    `new Product(3, "Đèn trùm",   500, new string[] {"Trắng"},               3),`
    `new Product(4, "Bàn học",    200, new string[] {"Trắng", "Xanh"},       1),`
    `new Product(5, "Túi da",     300, new string[] {"Đỏ", "Đen", "Vàng"},   2),`
    `new Product(6, "Giường ngủ", 500, new string[] {"Trắng"},               2),`
    `new Product(7, "Tủ áo",      600, new string[] {"Trắng"},               3),`
`};`
```

Giờ mình in ra các sản phẩm có giá = 400
Với LinQ:

```c#
public static void ProductPrice500()
{
	var ketqua = from product in products
	where product.Price == 400
	select product;

	foreach (var product in ketqua)
        Console.WriteLine(product.ToString());
}
```

Không sử dụng LinQ:

```c#
public static void ProductPrice500()
{
	foreach (var product in products)
        if(product.Price == 400){
            Console.WriteLine(product.ToString());
        }
}
```

# .NET

Về cơ bản thì mình thấy syntax không khác gì mấy so với JAVA, build API cũng khá giống nên mình cũng ổn với phần này
