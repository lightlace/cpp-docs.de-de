---
title: runtime_error-Klasse
ms.date: 11/04/2016
f1_keywords:
- stdexcept/std::runtime_error
helpviewer_keywords:
- runtime_error class
ms.assetid: 4d0227bf-847b-45a2-a320-2351ebf98368
ms.openlocfilehash: c4c4436c32f5f23c6bea119e95b165631384f583
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451121"
---
# <a name="runtimeerror-class"></a>runtime_error-Klasse

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um Fehler zu melden, die mutmaßlich nur erkennbar sind, wenn das Programm ausgeführt wird.

## <a name="syntax"></a>Syntax

```cpp
class runtime_error : public exception {
public:
    explicit runtime_error(const string& message);

    explicit runtime_error(const char *message);

};
```

## <a name="remarks"></a>Hinweise

Der von der [exception-Klasse](../standard-library/exception-class.md) zurückgegebene Wert ist eine Kopie von **message**`.`[data](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Beispiel

```cpp
// runtime_error.cpp
// compile with: /EHsc /GR
#include <iostream>

using namespace std;

int main( )
{
// runtime_error
   try
   {
      locale loc( "test" );
   }
   catch ( exception &e )
   {
      cerr << "Caught " << e.what( ) << endl;
      cerr << "Type " << typeid( e ).name( ) << endl;
   };
}
/* Output:
Caught bad locale name
Type class std::runtime_error
*/
```

## <a name="requirements"></a>Anforderungen

**Header:** \<stdexcept>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[Exception-Klasse](../standard-library/exception-class.md)\
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)
