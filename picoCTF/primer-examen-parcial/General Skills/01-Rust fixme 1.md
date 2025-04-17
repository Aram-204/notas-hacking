# Descripción
Have you heard of Rust? Fix the syntax errors in this Rust file to print the flag!Download the Rust code [here](https://challenge-files.picoctf.net/c_verbal_sleep/3f0e13f541928f420d9c8c96b06d4dbf7b2fa18b15adbd457108e8c80a1f5883/fixme1.tar.gz).
Hints:
1. Cargo is Rust's package manager and will make your life easier. See the getting started page [here](https://doc.rust-lang.org/book/ch01-03-hello-cargo.html)
2. [println!](https://doc.rust-lang.org/std/macro.println.html)
3. Rust has some pretty great compiler error messages. Read them maybe?
# Solución
- Descargamos el código con wget
- Descomprimimos el archivo con el siguiente comando:
```
amv@LAPTOP-1MU6MBUF:~$ tar -xvzf fixme1.tar.gz
fixme1/
fixme1/Cargo.toml
fixme1/Cargo.lock
fixme1/src/
fixme1/src/main.rs
```
- Encontraremos algunas carpetas, por lo tanto entramos a la carpeta fixme1
- Utilizamos el comando cargo build para poder ver que errores hay en el código
- Nos dice que el error está en como terminamos la función en src/main
- Nos movemos al archivo para modificar lo necesario con nano
- Hacemos las modificaciones necesarias y nos quedará así:
```
use xor_cryptor::XORCryptor;

fn main() {
    // Key for decryption
    let key = String::from("CSUCKS"); // How do we end statements in Rust?

    // Encrypted flag values
    let hex_values = ["41", "30", "20", "63", "4a", "45", "54", "76", "01", >

    // Convert the hexadecimal strings to bytes and collect them into a vect>
    let encrypted_buffer: Vec<u8> = hex_values.iter()
        .map(|&hex| u8::from_str_radix(hex, 16).unwrap())
        .collect();

    // Create decrpytion object
    let res = XORCryptor::new(&key);
    if res.is_err() {
        return; // How do we return in rust?
    }
    let xrc = res.unwrap();

    // Decrypt flag and print it out
    let decrypted_buffer = xrc.decrypt_vec(encrypted_buffer);
    println!(
        "{}:?", // How do we print out a variable in the println function? 
        String::from_utf8_lossy(&decrypted_buffer)
    );
}
```
- Volvemos a ver los errores con cargo build
- No nos muestra ningun error , así que utilizamos cargo run para correr el código y nos dará la bandera
```
picoCTF{4r3_y0u_4_ru$t4c30n_n0w?}
```
# Notas adicionales
# Referencias