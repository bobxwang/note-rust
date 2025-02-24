- wasm-pack build --target web
   - bundler：编译成给webpack之类的脚手架使用
   - web：编译成web可直接使用
   - nodejs：编译成可通过require来加载的node模块
   - deno：编译成可通过import来加载的deno模块
   - no-modules：跟web类似，但更旧并且不能使用es模块
- 升级
  ```rustup update stable --force```
- 使用下划线关掉告警未使用的变量
  ```rust
  fn main() {
	let _x = 5;  // 虽然未使用此变量但不会警告
	let y = 6;   // 会警告存在未使用的变量
  }
  ```
- Clippy
>是一个Rust代码的lint工具集合，帮助开发者捕获常见的错误并改进代码质量
- rust-toolchain
>跟Cargo.toml平级的一个文件名，常见于团队开发，确保成员使用相同的工具链版本，文件内容一般如下
```toml
[toolchain]
channel = "stable" #使用稳定版工具链
components = ["rustfmt", "clippy"] #默认安装格式化及代码检测集
targets = ["x86_64-unknown-linux-gnu"]
```
