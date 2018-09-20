---
title: Durchlaufen der Auflistung der C++-Standard-Bibliothek für jede mit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- DTL collections, iterating over
ms.assetid: 9358ca29-b982-4a19-bbfd-bef50fe66c9a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 92934e3f00bb34e6adfe101b0fea7abbe03600c2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46383193"
---
# <a name="iterating-over-c-standard-library-collection-by-using-for-each"></a>Durchlaufen der Auflistung der C++-Standard-Bibliothek für jede mit

Die `for each` -Schlüsselwort kann verwendet werden, um eine C++-Standardbibliothek-Auflistung zu durchlaufen.

## <a name="all-platforms"></a>Alle Plattformen

Eine Auflistung von C++-Standardbibliothek ist auch bekannt als eine *Container*. Weitere Informationen finden Sie unter [C++-Standardbibliothekcontainer](../standard-library/stl-containers.md).

## <a name="examples"></a>Beispiele

Das folgende Codebeispiel verwendet `for each` zum Durchlaufen einer [ \<Map >](../standard-library/map.md).

```cpp
// for_each_stl.cpp
// compile with: /EHsc
#include <map>
#include <iostream>
#include <string>
using namespace std;

int main() {
   int retval  = 0;
   map<string, int> months;

   months["january"] = 31;
   months["february"] = 28;
   months["march"] = 31;
   months["april"] = 30;
   months["may"] = 31;
   months["june"] = 30;
   months["july"] = 31;
   months["august"] = 31;
   months["september"] = 30;
   months["october"] = 31;
   months["november"] = 30;
   months["december"] = 31;

   map<string, int> months_30;

   for each( pair<string, int> c in months )
      if ( c.second == 30 )
         months_30[c.first] = c.second;

   for each( pair<string, int> c in months_30 )
      retval++;

   cout << "Months with 30 days = " << retval << endl;
}
```

### <a name="output"></a>Ausgabe

```Output
Months with 30 days = 4
```

## <a name="example"></a>Beispiel

Das folgende Codebeispiel verwendet einen const-Verweis (`const&`) für eine Iterationsvariable mit C++-Standardbibliothek-Containern. Sie können einen Verweis verwenden (`&`) als eine Iterationsvariable für Sammlungen eines Typs, der als deklariert werden, kann eine *T*`&`.

```cpp
// for_each_stl_2.cpp
// compile with: /EHsc
#include <vector>
#include <iostream>
using namespace std;

int main() {
   int retval = 0;

   vector<int> col(3);
   col[0] = 10;
   col[1] = 20;
   col[2] = 30;

   for each( const int& c in col )
      retval += c;

   cout << "retval: " << retval << endl;
}
```

### <a name="output"></a>Ausgabe

```Output
retval: 60
```

## <a name="windows-runtime"></a>Windows-Runtime

Es gibt keine plattformspezifischen Hinweise zu dieser Funktion.

### <a name="requirements"></a>Anforderungen

Compileroption: **/ZW**

## <a name="common-language-runtime"></a>Common Language Runtime

Es gibt keine plattformspezifischen Hinweise zu dieser Funktion.

### <a name="requirements"></a>Anforderungen

Compileroption: **/clr**

## <a name="see-also"></a>Siehe auch

[for each in](../dotnet/for-each-in.md)<br/>
[Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)