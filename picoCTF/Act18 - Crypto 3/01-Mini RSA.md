# Descripción
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this: [ciphertext](https://mercury.picoctf.net/static/a24cf907007a19dbf30310acad0df9e5/ciphertext)
Hints:
1. RSA [tutorial](https://en.wikipedia.org/wiki/RSA_\(cryptosystem\))
2. How could having too small of an `e` affect the security of this key?
3. Make sure you don't lose precision, the numbers are pretty big (besides the `e` value)
4. You shouldn't have to make _too_ many guesses
5. `pico` is in the flag, but not at the beginning
# Solución
- Obtenemos el archivo que nos dan con wget
- Le hacemos cat para ver el contenido y veremos que contiene el mensaje cifrado, así como los valores de e y N
- Nos podemos dar una idea de que tratan de que saquemos la raíz cúbica de N
- Hacemos un script en python usando la librería gmpy2, que nos permite hacer operaciones con números grandes
- Asignamos los valores que nos dan a las variables
- Intentamos distintos valores para poder extraer una raíz cubica exacta a partir de la suma c + k por N
- Si se encuentra una raíz cubica exacta, es posible desencriptar el texto y obtener la bandera.

`from gmpy2 import iroot`
`N=16157656843214630540782260519598878842336783177348929017407633211352136367960754624019502746024050951385898>e=3`
`c=12200123185888718861325247578988844221745345580555937133090883049102739910735547326599771339806853708992578>`
`for k in range(1, 100000):`
    `candidate = c + k * N`
    `m_root, exact = iroot(candidate, e)`
    `if exact:`
        `print(f"[+] Se encontro raiz exacta={k}")`
        `print("Texto numerico:", m_root)`
        `print("Texto desencriptado:", bytes.fromhex(hex(m_root)[2:]))`
        `break`
```
amv@LAPTOP-1MU6MBUF:~$ python3 desencriptado.py
[+] Se encontro raiz exacta=3533
Texto numerico: 1787330808968142828287809319332701517353332911736848279839502759158602467824780424488141955644417387373185756944952906538004355347478978500948630620749868180414755933760446136287315896825929319145984883756667607031853695069891380871892213007874933611243319812691520078269033745367443951846845107464675742664639073699800384973262142189949
Texto desencriptado: b'                                                                                                        picoCTF{e_sh0u1d_b3_lArg3r_0b39bbb1}'

picoCTF{e_sh0u1d_b3_lArg3r_0b39bbb1}
```
# Notas adicionales
# Referencias