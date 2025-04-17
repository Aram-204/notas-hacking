# Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/dcdaf491b35c1d0f5075e9583edbbb7aaea1dffb6ad32bc000e4d87b5200ff7b/fixme3.tar.gz).
Hints:
1. Read the comments...darn it!
# Solución
- Obtenemos el archivo con wget
- entramos a la carpeta fixme3
- Usamos cargo build para compilar y ver los errores existentes, en mi caso tengo que especificar que sea de manera incremental para evitar errores
```
┌──(kali㉿kali)-[~/hacking/fixme3]
└─$ CARGO_INCREMENTAL=0 cargo build
   Compiling crossbeam-utils v0.8.20
   Compiling rayon-core v1.12.1
   Compiling either v1.13.0
   Compiling crossbeam-epoch v0.9.18
   Compiling crossbeam-deque v0.8.5
   Compiling rayon v1.10.0
   Compiling xor_cryptor v1.2.3
   Compiling rust_proj v0.1.0 (/home/kali/hacking/fixme3)
error[E0133]: call to unsafe function `std::slice::from_raw_parts` is unsafe and requires unsafe function or block
  --> src/main.rs:31:31
   |
31 |         let decrypted_slice = std::slice::from_raw_parts(decrypted_ptr, decrypted_len);
   |                               ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ call to unsafe function                                                                                           
   |
   = note: consult the function's documentation for information on how to avoid undefined behavior

For more information about this error, try `rustc --explain E0133`.
error: could not compile `rust_proj` (bin "rust_proj") due to 1 previous error
```
- Vamos al main para modificar los errores
- Podremos ver en un comentario que nos dice que en cargo algunas veces debemos hacer cosas "unsafe"
- Quitamos como comentario la línea unsafe { }
- Ejecutamos el archivo, en mi caso especificamos de manera incremental para evitar errores
```
┌──(kali㉿kali)-[~/hacking/fixme3/src]
└─$ CARGO_INCREMENTAL=0 cargo run
   Compiling rust_proj v0.1.0 (/home/kali/hacking/fixme3)
    Finished `dev` profile [unoptimized + debuginfo] target(s) in 13.39s
     Running `/home/kali/hacking/fixme3/target/debug/rust_proj`
Using memory unsafe languages is a: PARTY FOUL! Here is your flag: picoCTF{n0w_y0uv3_f1x3d_1h3m_411}

picoCTF{n0w_y0uv3_f1x3d_1h3m_411}
```
# Notas adicionales
# Referencias