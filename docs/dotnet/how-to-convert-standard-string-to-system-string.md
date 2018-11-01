---
title: 'Gewusst wie: Konvertieren einer Standardzeichenfolge nach System::String'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting strings to System::String
- string conversion [C++], C++ Standard Library string
- strings [C++], converting
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
ms.openlocfilehash: 5c09ac5e86066e4382c511dce45e4ec6e5301d54
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575564"
---
# <a name="how-to-convert-standard-string-to-systemstring"></a>Gewusst wie: Konvertieren einer Standardzeichenfolge nach System::String

In diesem Thema wird das Konvertieren einer C++-Standardbibliothek ([\<Zeichenfolge >](../standard-library/string.md)) zu einem <xref:System.String>.

## <a name="example"></a>Beispiel

```
// convert_standard_string_to_system_string.cpp
// compile with: /clr
#include <string>
#include <iostream>
using namespace System;
using namespace std;

int main() {
   string str = "test";
   cout << str << endl;
   String^ str2 = gcnew String(str.c_str());
   Console::WriteLine(str2);

   // alternatively
   String^ str3 = gcnew String(str.c_str());
   Console::WriteLine(str3);
}
```

```Output
test
test
test
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)