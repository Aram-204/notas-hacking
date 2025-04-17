# Descripción
The Rust saga continues? I ask you, can I borrow that, pleeeeeaaaasseeeee?Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/babfbee79718a6363826ba86300173ffde6d81577e9dd07d4130c53a7eecf6c3/fixme2.tar.gz).
Hints:
1. https://doc.rust-lang.org/book/ch04-02-references-and-borrowing.html
# Solución
- Descargamos el archivo usando wget
- entramos a la carpeta fixme2
- Usamos cargo build para ver los errores que hay
- Identificamos los errores y los corregimos en el main
- Ahora usamos cargo run para ejecutar el programa y nos dará la bandera
```
picoCTF{4r3_y0u_h4v1n5_fun_y31?}
```
# Notas adicionales
- En mi caso tuve problemas con la compilación, así que tuve que especificar tanto en la compilación como al momento de correr para que lo hiciera de manera incremental
```
┌──(kali㉿kali)-[~/hacking/fixme2/src]
└─$ CARGO_INCREMENTAL=0 cargo build
   Compiling rust_proj v0.1.0 (/home/kali/hacking/fixme2)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 14.20s
┌──(kali㉿kali)-[~/hacking/fixme2/src]
└─$ CARGO_INCREMENTAL=0 cargo run
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 5.49s
     Running `/home/kali/hacking/fixme2/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{4r3_y0u_h4v1n5_fun_y31?}

```
- Este error se puede deber a que lo estoy haciendo desde una VM y esto tiene ciertas restricciones
# Referencias