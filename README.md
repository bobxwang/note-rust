- wasm-pack build --target web
   - bundler：编译成给webpack之类的脚手架使用
   - web：编译成web可直接使用
   - nodejs：编译成可通过require来加载的node模块
   - deno：编译成可通过import来加载的deno模块
   - no-modules：跟web类似，但更旧并且不能使用es模块
- 升级
  ```rustup update stable --force```
- 使用下划线关掉告警未使用的变量
  ```fn main() {
	let _x = 5;  // 虽然未使用此变量但不会警告
	let y = 6;   // 会警告存在未使用的变量
  }```
