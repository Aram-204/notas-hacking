# Descripción
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/3cfeb09681369c26e3f19d886bc1e5d9/values)
Hints:
1. Bits are expensive, I used only a little bit over 100 to save money
# Solución
1. Para obtener `d` se necesita saber el valor de `tn` y para él se necesita tener `p` y `q`, se puede probar factorizando `n`.
```python
c = 8533139361076999596208540806559574687666062896040360148742851107661304651861689
n = 769457290801263793712740792519696786147248001937382943813345728685422050738403253
e = 65537
```

2. La pagina factorDB nos indica que existe una factorización con dos numeros, por lo que obtenemos los siguientes valores:

```python
p = 1617549722683965197900599011412144490161
q = 475693130177488446807040098678772442581573
```

3. Comprobamos que `p * q = n`

```python
>>> p * q
769457290801263793712740792519696786147248001937382943813345728685422050738403253
```

4. Calculamos `tn` y `d` para obtener la llave privada

```python
tn = (p-1) * (q-1)
d = pow(e, -1, tn)
```

5. Usando la siguiente formula, podemos descifrar el texto y despues lo decodificamos.

```python
m = pow(c,d,n)
m =
13016382529449106065927291425342535437996222135352905256639629442503647501498237
bytes.fromhex(hex(m)[2:])
b'picoCTF{sma11_N_n0_g0od_45369387}'
```
```
```
# Notas adicionales
# Referencias