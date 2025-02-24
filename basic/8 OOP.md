>Rust不是传统意义上的面向对象编程语言，但它一样提供了很多OOP的功能，比如结构体，枚举和特性。其设计哲学强调零成本抽象，安全性跟性能
##### 无传统继承，必须依赖组合跟特性
- 避免了继承的复杂性，继承容易导致代码层次过深难以维护，并可能出现菱形继承问题
- 零成本抽象，注重性能和简单高效的组合方式，将结构体嵌套到另一个结构体
```rust
struct Engine {
	horsepower: u32,
}
impl Engine {
	fn start(&self) {
		println!("Engine with {} horsepower is start", self.horsepower);
	} 
}
struct Car {
	engine: Engine,
	brand: String,
}
impl Car {
	fn new(brand: &str,horsepower: u32) -> Self {
		Car {
			engine: Engine { horsepower },
			brand: brand.to_string(),
		}
	}
	fn start(&self) {
		self.engine.start();
		println!("{} car is starting", self.brand);	
	}
}
fn main() {
	let car = Car::new("Tesls", 400);
	car.start();
}
```

##### 关于封装
封装就是对外的策略，可通过模块机制来实现最外层的封装，并且每个Rust文件都可以看作是一个模块，模块内元素可通过pub关键字对外表明
```Rust
pub struct ClassName {
	pub field:Type,
}
pub impl ClassName {
	fn some_method(&self) { 
	}
}
pub enum EnumName {
	A,
	B
}
pub impl EnumName {
	fn some_method(&self) {
	}
}
```
##### 关于继承
继承是多态思想的实现，金态指的是编程语言可以处理多种类型数据的代码，在Rust可通过特性来实现多态，但特性无法实现属性的继承，只能实现类似于“接口”行为的功能