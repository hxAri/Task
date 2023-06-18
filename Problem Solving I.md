
# Problem Solving I

Diberikan bilangan array nums dan target berupa integer, kembalikan nilai dari dua angka dimana hasil penjumlahan dua angka tersebut sama dengan nilai target.
Dapat diasumsikan bahwa setiap input memiliki satu solusi, dan tidak diperbolehkan untuk menggunakan elemen yang sama dua kali.

## Contoh 1
Input ```nums = [ 2, 7, 11, 15 ], target = 9```<br/>
Output ```[ 0, 1 ]```

## Penjelasan
Karena ```nums[0] + nums[1]``` adalah ```9```, sehingga nilai yang dikembalikan ```[ 0, 1 ]```

## Contoh 2
Input ```nums = [3,3], target = 6```<br/>
Output ```[0, 1]```

## Batasan
* ```2 <= nums.length <= 104```
* ```-109 <= nums[i] <= 109```
* ```-109 <= target <= 109```
* Hanya satu jawaban

## Implementasi
```py
#[sum( list nums, int target )]: list
def sum( nums:list, target:int ):
    
    # Dictionary untuk menyimpan nilai dan indeks angka.
    num_dict = {}
    
    for i, num in enumerate( nums ):
        
        # Angka yang harus dicari
        complement = target - num
        
        if complement in num_dict:
            
            # Mengembalikan indeks pasangan angka.
            return [num_dict[complement], i]
        
        # Menyimpan angka dan indeksnya dalam dictionary.
        num_dict[num] = i
    
    # Jika tidak ditemukan pasangan angka.
    return []
```

## Penjelasan
Pada implementasi di atas, fungsi menggunakan dictionary `num_dict` untuk menyimpan nilai dan indeks angka dalam array nums.
Kemudian melakukan iterasi pada setiap angka dalam array `nums`.
Untuk setiap angka, akan mencari nilai yang harus ada agar penjumlahannya dengan angka tersebut sama dengan target.
Jika nilai tersebut ada dalam dictionary `num_dict`, fungsi akan mengembalikan indeks pasangan angka tersebut.
Jika pasangan angka tidak ditemukan, maka fungsi akan mengembalikan array kosong `[]`.

## Pengujian
Untuk uji coba, kita bisa langsung menggunakan cara berikut:
```py
# Maksimal iterasi.
max = 100

# Generate angka.
nums = [ idx * 4 for idx in range( max ) ]

for i in range( max ):
    print( "input >> {} Output >> {}".format( i, sum( nums, i ) ) )
```

#### Output
```
input >> 0 Output >> []
input >> 1 Output >> []
input >> 2 Output >> []
input >> 3 Output >> []
input >> 4 Output >> [0, 1]
input >> 5 Output >> []
input >> 6 Output >> []
input >> 7 Output >> []
input >> 8 Output >> [0, 2]
input >> 9 Output >> []
input >> 10 Output >> []
input >> 11 Output >> []
input >> 12 Output >> [1, 2]
input >> 13 Output >> []
input >> 14 Output >> []
input >> 15 Output >> []
input >> 16 Output >> [1, 3]
input >> 17 Output >> []
input >> 18 Output >> []
input >> 19 Output >> []
input >> 20 Output >> [2, 3]
input >> 21 Output >> []
input >> 22 Output >> []
input >> 23 Output >> []
input >> 24 Output >> [2, 4]
...
```
