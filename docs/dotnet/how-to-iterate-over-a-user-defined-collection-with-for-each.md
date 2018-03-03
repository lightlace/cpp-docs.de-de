---
title: "Vorgehensweise: Durchlaufen einer benutzerdefinierten Sammlung mit für die einzelnen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- collections, iterating over
ms.assetid: 0efd9e3c-d7bb-4f6c-9938-e0e65d191433
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 2d0c4c714cb9cf605de5cf42cf922a74d09146c5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-iterate-over-a-user-defined-collection-with-for-each"></a>Gewusst wie: Durchlaufen einer benutzerdefinierten Auflistung mit der for-each-Klausel
Bei einer Klasse eine verwaltete Auflistung ist, muss sein Status eine nicht privaten GetEnumerator-Funktion, die ein Handle auf eine Enumeratorklasse oder eine Schnittstelle zurückgibt.  Eine Enumerator-Klasse muss die Deklaration für nicht statische MoveNext-Funktion und Current-Eigenschaft enthalten.  
  
## <a name="example"></a>Beispiel  
 Einfache benutzerdefinierte Sammlung mit Verweistypen.  
  
```  
// for_each_user_defined_collections.cpp  
// compile with: /clr  
using namespace System;  
public interface struct IMyEnumerator {  
   bool MoveNext();  
   property Object^ Current {  
      Object^ get();  
   }  
   void Reset();  
};  
  
public ref struct MyArray {     
  
   MyArray( array<int>^ d ) {  
      data = d;  
   }  
  
   ref struct enumerator : IMyEnumerator {  
      enumerator( MyArray^ myArr ) {  
         colInst = myArr;  
         currentIndex = -1;  
      }  
  
      virtual bool MoveNext() {  
         if( currentIndex < colInst->data->Length - 1 ) {  
            currentIndex++;  
            return true;  
         }  
         return false;  
      }  
  
      property Object^ Current {  
         virtual Object^ get() {  
            return colInst->data[currentIndex];  
         }  
      };  
  
      virtual void Reset() {}  
      ~enumerator() {}  
  
      MyArray^ colInst;  
      int currentIndex;  
   };  
  
   array<int>^ data;  
  
   IMyEnumerator^ GetEnumerator() {  
      return gcnew enumerator(this);  
   }  
};  
  
int main() {  
   int retval = 0;  
  
   MyArray^ col = gcnew MyArray( gcnew array<int>{10, 20, 30 } );  
  
   for each ( Object^ c in col )  
      retval += (int)c;  
  
   retval -= 10 + 20 + 30;  
  
   for each ( int c in gcnew MyArray( gcnew array<int>{10, 20, 30 } ) )  
      retval += c;  
  
   retval -= 10 + 20 + 30;  
  
   Console::WriteLine("Return Code: {0}", retval );  
   return retval;  
}  
```  
  
```Output  
Return Code: 0  
```  
  
## <a name="see-also"></a>Siehe auch  
 [for each in](../dotnet/for-each-in.md)