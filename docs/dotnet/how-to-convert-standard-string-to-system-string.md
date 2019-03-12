---
title: 'Vorgehensweise: Konvertieren einer Standardzeichenfolge nach System:: String'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- C++ Standard Library, converting strings to System::String
- string conversion [C++], C++ Standard Library string
- strings [C++], converting
ms.assetid: 1fde79a0-9d0b-44e5-981b-e8f2676c199d
ms.openlocfilehash: e1fca0e8cb614c111af80324793cf8027be333a0
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749972"
---
# <a name="how-to-convert-standard-string-to-systemstring"></a>Vorgehensweise: Konvertieren einer Standardzeichenfolge nach System:: String

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
