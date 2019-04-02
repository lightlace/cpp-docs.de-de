---
title: 'Vorgehensweise: Zugreifen auf Zeichen in einem System:: String'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
ms.openlocfilehash: 6b9e30a18ab1d2b8463ccccae0b265bc20904020
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775971"
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Vorgehensweise: Zugreifen auf Zeichen in einem System:: String

Sie erreichen die Zeichen einer <xref:System.String> -Objekt für Hochleistungs-Aufrufe nicht verwalteten Funktionen, `wchar_t*` Zeichenfolgen. Die Methode wird ein innerer Zeiger auf das erste Zeichen von der <xref:System.String> Objekt. This-Zeiger kann direkt bearbeitet oder angeheftet und übergeben Sie an eine Funktion erwartet eine gewöhnliche `wchar_t` Zeichenfolge.

## <a name="example"></a>Beispiel

`PtrToStringChars` Gibt eine <xref:System.Char>, d.h. ein innerer Zeiger (auch bekannt als eine `byref`). Daher ist es während der Garbagecollection. Sie müssen diesen Zeiger anheften, es sei denn, man es an eine native Funktion übergeben.

Betrachten Sie folgenden Code.  Anheften von Zertifikaten ist nicht erforderlich, da `ppchar` ein innerer Zeiger ist, und wenn der Garbage Collector die Zeichenfolge das Objekt zeigt verschiebt auf, auch aktualisiert `ppchar`. Ohne eine [Pin_ptr (C++ / CLI)](../extensions/pin-ptr-cpp-cli.md), funktioniert der Code, und haben nicht die potenziellen Leistungseinbußen durch Anheften von verursacht.

Wenn Sie übergeben `ppchar` an eine native Funktion, klicken Sie dann es muss eine feste Zeiger, da der Garbage Collector keine Zeiger auf den nicht verwalteten Stapelrahmen zu aktualisieren.

```
// PtrToStringChars.cpp
// compile with: /clr
#include<vcclr.h>
using namespace System;

int main() {
   String ^ mystring = "abcdefg";

   interior_ptr<const Char> ppchar = PtrToStringChars( mystring );

   for ( ; *ppchar != L'\0'; ++ppchar )
      Console::Write(*ppchar);
}
```

```Output
abcdefg
```

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt an, in dem Anheften von Zertifikaten benötigt wird.

```
// PtrToStringChars_2.cpp
// compile with: /clr
#include <string.h>
#include <vcclr.h>
// using namespace System;

size_t getlen(System::String ^ s) {
   // Since this is an outside string, we want to be secure.
   // To be secure, we need a maximum size.
   size_t maxsize = 256;
   // make sure it doesn't move during the unmanaged call
   pin_ptr<const wchar_t> pinchars = PtrToStringChars(s);
   return wcsnlen(pinchars, maxsize);
};

int main() {
   System::Console::WriteLine(getlen("testing"));
}
```

```Output
7
```

## <a name="example"></a>Beispiel

Ein innerer Zeiger hat alle Eigenschaften der systemeigenen C++-Zeigers. Beispielsweise können Sie es zum Durchlaufen einer verknüpften Datenstruktur und Einfüge-und Löschvorgänge mit nur einem Zeiger:

```
// PtrToStringChars_3.cpp
// compile with: /clr /LD
using namespace System;
ref struct ListNode {
   Int32 elem;
   ListNode ^ Next;
};

void deleteNode( ListNode ^ list, Int32 e ) {
   interior_ptr<ListNode ^> ptrToNext = &list;
   while (*ptrToNext != nullptr) {
      if ( (*ptrToNext) -> elem == e )
         *ptrToNext = (*ptrToNext) -> Next;   // delete node
      else
         ptrToNext = &(*ptrToNext) -> Next;   // move to next node
   }
}
```

## <a name="see-also"></a>Siehe auch

[Verwenden von C++-Interop (implizites PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)
