---
title: 'Vorgehensweise: Zugreifen auf Zeichen in einem System:: String | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- characters [C++], accessing in System::String
- examples [C++], strings
- strings [C++], accessing characters
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2cc927d2e06def1eba726f3123e9968003e62d1b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-access-characters-in-a-systemstring"></a>Gewusst wie: Zugriff auf Zeichen in einem System::String
Sie erreichen die Zeichen einer <xref:System.String> Objekt für hohe Leistung Aufrufe nicht verwalteten Funktionen, `wchar_t*` Zeichenfolgen. Die Methode wird ein innerer Zeiger auf das erste Zeichen von der <xref:System.String> Objekt. This-Zeiger kann direkt bearbeitet oder fixiert und übergeben werden an eine Funktion erwartet eine gewöhnliche `wchar_t` Zeichenfolge.  
  
## <a name="example"></a>Beispiel  
 `PtrToStringChars`Gibt eine <xref:System.Char>, also ein innerer Zeiger (auch bekannt als ein `byref`). Daher ist es Garbage collection. Sie haben keine this-Zeiger anheften, es sei denn, sie an eine systemeigene Funktion übergeben werden sollen.  
  
 Betrachten Sie folgenden Code.  Anheften ist nicht erforderlich, da `ppchar` ein innerer Zeiger, und wenn der Garbage Collector die Zeichenfolge das Objekt zeigt verschiebt auf, aktualisiert es auch `ppchar`. Ohne eine [Pin_ptr (C + c++ / CLI)](../windows/pin-ptr-cpp-cli.md), funktioniert der Code und nicht die potenzielle Leistungseinbußen verursacht sein anheften.  
  
 Wenn Sie übergeben `ppchar` an eine systemeigene Funktion anschließend muss er eine feste Zeiger, da der Garbage Collector keine Verweise auf den nicht verwalteten Stapelrahmen aktualisieren kann.  
  
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
 Dieses Beispiel zeigt, in denen anheften erforderlich ist.  
  
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
 Ein innerer Zeiger hat alle Eigenschaften eines systemeigenen C++-Zeigers. Beispielsweise können Sie es auf eine verknüpfte Datenstruktur zu durchlaufen und Einfüge-und Löschvorgänge mit nur einem Zeiger:  
  
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