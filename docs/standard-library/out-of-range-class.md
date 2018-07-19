---
title: out_of_range-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- stdexcept/std::out_of_range
dev_langs:
- C++
helpviewer_keywords:
- out_of_range class
ms.assetid: d0e14dc0-065e-4666-9ac9-51e52223c503
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aeb29538dc73ddbefe2ee443cf7f8bfa660eb528
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852864"
---
# <a name="outofrange-class"></a>out_of_range-Klasse

Die Klasse fungiert als Basisklasse für alle Ausnahmen, die ausgelöst werden, um ein Argument zu melden, dessen Wert außerhalb seines zulässigen Bereichs liegt.

## <a name="syntax"></a>Syntax

```cpp
class out_of_range : public logic_error {
public:
    explicit out_of_range(const string& message);

    explicit out_of_range(const char *message);

};
```

## <a name="remarks"></a>Hinweise

Der von [Was](../standard-library/exception-class.md) zurückgegebene Wert ist eine Kopie von **Nachricht**`.`[Daten](../standard-library/basic-string-class.md#data).

## <a name="example"></a>Beispiel

```cpp
// out_of_range.cpp
// compile with: /EHsc
#include <string>
#include <iostream>

using namespace std;

int main() {
// out_of_range
   try {
      string str( "Micro" );
      string rstr( "soft" );
      str.append( rstr, 5, 3 );
      cout << str << endl;
   }
   catch ( exception &e ) {
      cerr << "Caught: " << e.what( ) << endl;
   };
}
```

## <a name="output"></a>Ausgabe

```cpp
Caught: invalid string position
```

## <a name="requirements"></a>Anforderungen

**Header:** \<stdexcept>

**Namespace:** std

## <a name="see-also"></a>Siehe auch

[logic_error-Klasse](../standard-library/logic-error-class.md)<br/>
[Threadsicherheit in der C++-Standardbibliothek](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
