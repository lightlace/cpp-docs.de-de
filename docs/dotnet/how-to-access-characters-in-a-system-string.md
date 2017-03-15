---
title: "Gewusst wie: Zugriff auf Zeichen in einem System::String | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Zeichen [C++], Zugriff in System::String"
  - "Beispiele [C++], Zeichenfolgen"
  - "Zeichenfolgen [C++], Zugreifen auf Zeichen"
ms.assetid: cfc89756-aef3-4988-907e-fb236dcb7087
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Gewusst wie: Zugriff auf Zeichen in einem System::String
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können auf die Zeichen in einem <xref:System.String> zugreifen, um Hochleistungsaufrufe auf nicht verwaltete Funktionen zu implementieren, die `wchar_t*`\-Zeichenfolgen akzeptieren.  Bei dieser Methode wird ein innerer Zeiger auf das erste Zeichen des <xref:System.String>\-Objekts erstellt.  Dieser Zeiger kann direkt bearbeitet oder fixiert und an eine Funktion übergeben werden, die eine gewöhnliche `wchar_t`\-Zeichenfolge erwartet.  
  
## Beispiel  
 `PtrToStringChars` gibt einen <xref:System.Char> zurück, der ein innerer Zeiger \(auch als `byref` bezeichnet\) ist.  Als solcher unterliegt er der Garbage Collection.  Sie müssen diesen Zeiger nur fixieren, wenn er an eine systemeigene Funktion übergeben wird.  
  
 Betrachten Sie folgenden Code.  Es ist keine Fixierung erforderlich, da `ppchar` ein innerer Zeiger ist. Wenn der Garbage Collector die Zeichenfolge verschiebt, auf den der Zeiger verweist, wird auch `ppchar` aktualisiert.  Ohne einen [pin\_ptr \(C\+\+\/CLI\)](../windows/pin-ptr-cpp-cli.md) funktioniert der Code und ist nicht von der potenziellen Leistungsbeeinträchtigung bei einer Fixierung betroffen.  
  
 Wenn `ppchar`  an eine systemeigene Funktion übergeben wird, muss ein fester Zeiger verwendet werden, da der Garbage Collector keine Zeiger auf dem nicht verwalteten Stapelrahmen aktualisieren kann.  
  
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
  
  **abcdefg**   
## Beispiel  
 Dieses Beispiel zeigt, wo ein Fixieren notwendig ist.  
  
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
  
 **7**   
## Beispiel  
 Ein innerer Zeiger verfügt über alle Eigenschaften eines systemeigenen C\+\+\-Zeigers.  Sie können ihn z. B. verwenden, um eine verknüpfte Datenstruktur zu durchlaufen und Einfüge\- und Löschvorgänge mit nur einem Zeiger durchzuführen:  
  
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
  
## Siehe auch  
 [Verwenden von C\+\+\-Interop \(implizites PInvoke\)](../dotnet/using-cpp-interop-implicit-pinvoke.md)