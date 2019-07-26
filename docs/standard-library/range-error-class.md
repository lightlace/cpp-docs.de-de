---
title: range_error-Klasse
ms.date: 08/14/2018
f1_keywords:
- stdexcept/std::range_error
helpviewer_keywords:
- range_error class
ms.assetid: 8afb3e88-fc49-4213-b096-ed63d7aea37c
ms.openlocfilehash: 3e741604a3bb23fa8166023d115f79e7a288e2f7
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68458246"
---
# <a name="rangeerror-class"></a>range_error-Klasse

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um einen Bereichsfehler zu melden.

## <a name="syntax"></a>Syntax

```cpp
class range_error : public runtime_error {
public:
    explicit range_error(const string& message);
    explicit range_error(const char *message);
};
```

## <a name="remarks"></a>Hinweise

Der von [was](../standard-library/exception-class.md) zurückgegebene Wert ist eine Kopie `message.data`von. Weitere Informationen finden Sie unter [basic_string::d ATA](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Beispiel

```cpp
// range_error.cpp
// compile with: /EHsc /GR
#include <iostream>
using namespace std;
int main()
{
   try
   {
      throw range_error( "The range is in error!" );
   }
   catch (range_error &e)
   {
      cerr << "Caught: " << e.what( ) << endl;
      cerr << "Type: " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught: The range is in error!
Type: class std::range_error
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<stdexcept>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[runtime_error-Klasse](../standard-library/runtime-error-class.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
