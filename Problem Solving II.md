
# Problem Solving II

Diberikan sebuah bilangan bulat/integer `x`, dengan nilai kembalian `true` jika `x` merupakan palindrome.
Bilangan bulat bisa dikatakan palindrome ketika memiliki nilai yang sama jika dibaca dari depan maupun sebaliknya.
Sebagai contoh, `141` merupakan palindrome namun `145` bukan palindrome.

## Contoh 1
Input ```x = 141```<br/>
Output ```True```

## Contoh 2
Input ```x = 345```<br/>
Output ```False```

## Implementasi
```py
#[isPalindrome( int x )]: bool
def isPalindrome( x:int ):
	
    # Mengubah bilangan menjadi string.
    x_str = str( x )
    
    # Cek apakah string x_str sama dengan string x_str yang dibalik.
    if x_str == x_str[::-1]:
        return True
    else:
        return False
```

## Pengujian
Untuk uji coba bisa langsung kita bisa menggunakan cara berikut:
```py
# Maksimal iterasi.
max = 100

for i in range( max ):
	n = i * 3
	print( "input >> {} >> Palindrome ?? {}".format( n, isPalindrome( n ) ) )
```

#### Output
```
input >> 0 >> Palindrome ?? True
input >> 3 >> Palindrome ?? True
input >> 6 >> Palindrome ?? True
input >> 9 >> Palindrome ?? True
input >> 12 >> Palindrome ?? False
input >> 15 >> Palindrome ?? False
input >> 18 >> Palindrome ?? False
input >> 21 >> Palindrome ?? False
input >> 24 >> Palindrome ?? False
input >> 27 >> Palindrome ?? False
input >> 30 >> Palindrome ?? False
input >> 33 >> Palindrome ?? True
input >> 36 >> Palindrome ?? False
input >> 39 >> Palindrome ?? False
input >> 42 >> Palindrome ?? False
input >> 45 >> Palindrome ?? False
input >> 48 >> Palindrome ?? False
input >> 51 >> Palindrome ?? False
input >> 54 >> Palindrome ?? False
...
```
