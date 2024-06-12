# 装饰器模式Decorator Pattern
```rust
pub trait BaseIO {
    fn read(&mut self);
    fn write(&mut self);
}

pub struct IO;

// IO仅仅包含基本的读写功能
impl BaseIO for IO {
    fn read(&mut self) {
        todo!()
    }

    fn write(&mut self) {
        todo!()
    }
}

// 加密装饰器,内部封装对象
pub struct Encryption<T: BaseIO> {
    inner: T
}

// 扩展封装对象的功能:加密
impl<T: BaseIO> BaseIO for Encryption<T> {
    fn read(&mut self) {
        // encrypt

        //then read
        self.inner.read()
    }

    fn write(&mut self) {
        // encrypt

        //then write
        self.inner.write()
    }
}

// 压缩装饰器,内部封装对象
pub struct Compress<T: BaseIO> {
    inner: T
}
// 扩展封装对象的功能:压缩
impl<T: BaseIO> BaseIO for Compress<T> {
    fn read(&mut self) {
        //
    }

    fn write(&mut self) {
        //compress

        self.inner.write();
    }
}

fn main() {
    let base_io = IO;
    let mut e = Encryption { inner: base_io };  //封装
    let mut e = Compress { inner: e };  // 再次封装
    e.read();
}
```