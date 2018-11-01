---
title: complex&lt;long double&gt;
ms.date: 11/04/2016
f1_keywords:
- std::complex<long double>
- complex<long double>
- std.complex<long double>
helpviewer_keywords:
- complex<long double> function
ms.assetid: 37591991-b385-46e9-b727-d534dbc10432
ms.openlocfilehash: 19d4569523879911209bf0c05e762eba2c9852a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456575"
---
# <a name="complexltlong-doublegt"></a>complex&lt;long double&gt;

Diese explizit spezialisierte Vorlagenklasse beschreibt ein Objekt, das ein geordnetes Paar von Objekten, beide vom Typ speichert **long double**, wird das erste Objekt den reellen Teil einer komplexen Zahl und das zweite Objekt dem imaginären Teil.

## <a name="syntax"></a>Syntax

```cpp
template <>
class complex<long double> {
public:
    constexpr complex(
    long double _RealVal = 0,
    long double _ImagVal = 0);

complex(
    constexpr complex<long double>& complexNum);

// rest same as template class complex
};
```

### <a name="parameters"></a>Parameter

*_RealVal*<br/>
Der Wert des Typs **long double** für den Realteil der komplexen Zahl, die erstellt wird

*_ImagVal*<br/>
Der Wert des Typs **long double** für den imaginären Teil der komplexen Zahl, die erstellt wird.

*complexNum*<br/>
Die komplexe Zahl vom Typ **doppelte** oder eines Typs **"float"** , deren tatsächliche und imaginäre Teile werden verwendet, um eine komplexe Zahl des Typs initialisieren **long double** erstellt wird.

## <a name="return-value"></a>Rückgabewert

Eine komplexe Zahl vom Typ **long double**.

## <a name="remarks"></a>Hinweise

Die explizite Spezialisierung der Vorlagenklasse `complex` in eine komplexe Klasse des Typs **long double** unterscheidet sich von der Vorlagenklasse nur in den Konstruktoren, die sie definiert. Die Konvertierung von **long double** zu **"float"** darf implizit erfolgen, aber die Konvertierung von **doppelte** zu **long double** ist erforderlich sollen **explizite**. Die Verwendung einer **expliziten** Konvertierung schließt die Initiierung mit Typkonvertierung über die Zuweisungssyntax aus.

Weitere Informationen zur Vorlagenklasse `complex` und ihre Member, finden Sie unter [complex-Klasse](../standard-library/complex-class.md).

**Microsoft-spezifisch**: die **long double** und **doppelte** Typen die gleiche Darstellung haben, aber unterschiedliche Typen sind. Weitere Informationen finden Sie unter [Basistypen](../cpp/fundamental-types-cpp.md).

## <a name="example"></a>Beispiel

```cpp
// complex_comp_ld.cpp
// compile with: /EHsc
#include <complex>
#include <iostream>

int main( )
{
    using namespace std;
    double pi = 3.14159265359;

    // The first constructor specifies real & imaginary parts
    complex<long double> c1( 4.0 , 5.0 );
    cout << "Specifying initial real & imaginary parts,\n"
        << " as type float gives c1 = " << c1 << endl;

    // The second constructor initializes values of the real &
    // imaginary parts using those of complex number of type float
    complex<float> c2float( 1.0 , 3.0 );
    complex<long double> c2longdouble ( c2float );
    cout << "Implicit conversion from type float to type long double,"
        << "\n gives c2longdouble = " << c2longdouble << endl;

    // The third constructor initializes values of the real &
    // imaginary parts using those of a complex number
    // of type double
    complex<double> c3double( 3.0 , 4.0 );
    complex<long double> c3longdouble( c3double );
    cout << "Implicit conversion from type long double to type float,"
        << "\n gives c3longdouble = " << c3longdouble << endl;

    // The modulus and argument of a complex number can be recovered
    double absc3 = abs( c3longdouble );
    double argc3 = arg( c3longdouble );
    cout << "The modulus of c3 is recovered from c3 using: abs( c3 ) = "
        << absc3 << endl;
    cout << "Argument of c3 is recovered from c3 using:\n arg( c3 ) = "
        << argc3 << " radians, which is " << argc3 * 180 / pi
        << " degrees." << endl;
}
```

```Output
Specifying initial real & imaginary parts,
as type float gives c1 = (4,5)
Implicit conversion from type float to type long double,
gives c2longdouble = (1,3)
Implicit conversion from type long double to type float,
gives c3longdouble = (3,4)
The modulus of c3 is recovered from c3 using: abs( c3 ) = 5
Argument of c3 is recovered from c3 using:
arg( c3 ) = 0.927295 radians, which is 53.1301 degrees.
```

## <a name="requirements"></a>Anforderungen

**Header**: \<complex>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[complex-Klasse](../standard-library/complex-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
