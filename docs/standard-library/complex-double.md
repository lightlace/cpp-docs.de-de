---
title: complex&lt;double&gt; | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- complex/std::complex<double>
dev_langs:
- C++
helpviewer_keywords:
- complex<double> function
ms.assetid: 0d0b9d2a-9b9b-410b-82a0-86b6df127e47
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f17beb079b0b9e4f37cdf0ac2b3749e4ffc3790f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="complexltdoublegt"></a>complex&lt;double&gt;

Beschreibt ein Objekt, das ein geordnetes Paar von Objekten des Typs speichert **Double **** das erste Objekt den reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil.

## <a name="syntax"></a>Syntax

```cpp
template <>
class complex<double> {
public:
    constexpr complex(
    double RealVal = 0,
    double ImagVal = 0);

constexpr complex(const complex<double>& complexNum);

constexpr explicit complex(const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parameter

`RealVal` Der Wert des Typs **doppelte** für den reellen Teil der zu erstellenden komplexen Zahl.

`ImagVal` Der Wert des Typs **doppelte** für den imaginären Teil der zu erstellenden komplexen Zahl.

`complexNum` Die komplexe Zahl vom Typ **"float"** oder vom Typ `long double` , deren reellen und imaginären Teile werden verwendet, um eine komplexe Zahl des Typs initialisieren **doppelte** erstellt wird.

## <a name="return-value"></a>Rückgabewert

Eine komplexe Zahl vom Typ **double**.

## <a name="remarks"></a>Hinweise

Die explizite Spezialisierung der complex-Vorlagenklasse in eine komplexe Klasse des Typs **double** unterscheidet sich von der Vorlagenklasse nur in den Konstruktoren, die sie definiert. Die Konvertierung von **float** in **double** darf implizit erfolgen, aber die Konvertierung von `long double` in **double** muss **explizit** erfolgen. Die Verwendung einer **expliziten** Konvertierung schließt die Initiierung mit Typkonvertierung über die Zuweisungssyntax aus.

Weitere Informationen zur Vorlagenklasse `complex` finden Sie unter [complex-Klasse](../standard-library/complex-class.md). Eine Liste der Member der `complex`-Vorlagenklasse finden Sie unter .

## <a name="example"></a>Beispiel

```cpp
// complex_comp_dbl.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <double> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type double gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type float
   complex <float> c2float ( 4.0 , 5.0 );
   complex <double> c2double ( c2float );
   cout << "Implicit conversion from type float to type double,"
        << "\n gives c2double = " << c2double << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 4.0 , 5.0 );
   complex <double> c3double ( c3longdouble );
   cout << "Explicit conversion from type float to type double,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3longdouble );
   double argc3 = arg ( c3longdouble );
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:\n arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
\* Output:
Specifying initial real & imaginary parts,
 as type double gives c1 = (4,5)
Implicit conversion from type float to type double,
 gives c2double = (4,5)
Explicit conversion from type float to type double,
 gives c3longdouble = (4,5)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 6.40312
Argument of c3 is recovered from c3 using:
 arg ( c3 ) = 0.896055 radians, which is 51.3402 degrees.
*\
```

## <a name="requirements"></a>Anforderungen

**Header**: \<complex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[complex-Klasse](../standard-library/complex-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
