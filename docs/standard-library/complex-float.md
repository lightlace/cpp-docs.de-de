---
title: complex&lt;float&gt;
ms.date: 11/04/2016
f1_keywords:
- complex/std::complex<float>
helpviewer_keywords:
- complex<float> function
ms.assetid: 1178eb1e-39bd-4017-89cd-aea95f813939
ms.openlocfilehash: a09b6d0306f633754cad4b12a652eac557f96634
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279085"
---
# <a name="complexltfloatgt"></a>complex&lt;float&gt;

Beschreibt ein Objekt, das ein geordnetes Paar von Objekten des Typs speichert **"float"**, wird das erste Objekt den reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil.

## <a name="syntax"></a>Syntax

```cpp
template <>
class complex<float> {
public:
    constexpr complex(
    float _RealVal = 0,
    float _ImagVal = 0);

constexpr complex(
    const complex<float>& complexNum);

constexpr complex(
    const complex<double>& complexNum);

constexpr complex(
    const complex<long double>& complexNum);
// rest same as template class complex
};
```

### <a name="parameters"></a>Parameter

*_RealVal*<br/>
Der Wert vom Typ **float** für den Realteil der zu erstellenden komplexen Zahl.

*_ImagVal*<br/>
Der Wert vom Typ **float** für den Imaginärteil der zu erstellenden komplexen Zahl.

*complexNum*<br/>
Die komplexe Zahl vom Typ **doppelte** oder eines Typs **long double** , deren tatsächliche und imaginäre Teile werden verwendet, um eine komplexe Zahl des Typs initialisieren **"float"** erstellt wird.

## <a name="return-value"></a>Rückgabewert

Eine komplexe Zahl vom Typ **float**.

## <a name="remarks"></a>Hinweise

Die explizite Spezialisierung der complex-Vorlagenklasse in eine komplexe Klasse des Typs **float** unterscheidet sich von der Vorlagenklasse nur in den Konstruktoren, die sie definiert. Die Konvertierung von **"float"** zu **doppelte** darf implizit erfolgen, aber die weniger sichere Konvertierung von **"float"** zu **long double** ist muss **explizite**. Die Verwendung einer **expliziten** Konvertierung schließt die Initiierung mit Typkonvertierung über die Zuweisungssyntax aus.

Weitere Informationen zur Vorlagenklasse `complex` finden Sie unter [complex-Klasse](../standard-library/complex-class.md). Eine Liste der Member der `complex`-Vorlagenklasse finden Sie unter .

## <a name="example"></a>Beispiel

```cpp
// complex_comp_flt.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
   using namespace std;
   double pi = 3.14159265359;

   // The first constructor specifies real & imaginary parts
   complex <float> c1 ( 4.0 , 5.0 );
   cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

   // The second constructor initializes values of the real &
   // imaginary parts using those of complex number of type double
   complex <double> c2double ( 1.0 , 3.0 );
   complex <float> c2float ( c2double );
   cout << "Implicit conversion from type double to type float,"
        << endl << "gives c2float = " << c2float << endl;

   // The third constructor initializes values of the real &
   // imaginary parts using those of a complex number
   // of type long double
   complex <long double> c3longdouble ( 3.0 , 4.0 );
   complex <float> c3float ( c3longdouble );
   cout << "Explicit conversion from type long double to type float,"
        << endl << "gives c3float = " << c3float << endl;

   // The modulus and argument of a complex number can be recovered
   double absc3 = abs ( c3float);
   double argc3 = arg ( c3float);
   cout << "The modulus of c3 is recovered from c3 using: abs ( c3 ) = "
        << absc3 << endl;
   cout << "Argument of c3 is recovered from c3 using:"
        << endl << "arg ( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
/* Output:
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type double to type float,
gives c2float = (1,3)
Explicit conversion from type long double to type float,
gives c3float = (3,4)
The modulus of c3 is recovered from c3 using: abs ( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg ( c3 ) = 0.927295 radians, which is 53.1301 degrees.
*/
```

## <a name="requirements"></a>Anforderungen

**Header**: \<complex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[complex-Klasse](../standard-library/complex-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
