---
title: Compilerfehler C3510 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3510
dev_langs:
- C++
helpviewer_keywords:
- C3510
ms.assetid: c48387bc-0300-4a4d-97f7-3fb90f82a451
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: abb58d8d4fb9008b07579ef7fbc0066d00bcea57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3510"></a>Compilerfehler C3510
abhängigen Typ 'Typbib Bibliothek 'wurde' wurde nicht gefunden.  
  
 [No_registry](../../preprocessor/no-registry.md) und [Auto_search](../../preprocessor/auto-search.md) übergeben wurden, um `#import` , aber der Compiler konnte sich nicht um einen Verweistyp-Bibliothek zu finden.  
  
 Um diesen Fehler zu beheben, stellen Sie sicher, dass alle Typbibliotheken und referenzierten Typbibliotheken für den Compiler verfügbar sind.  
  
 Im folgende Beispiel wird C3510 generiert:  
  
 Angenommen, die folgenden zwei Typbibliotheken erstellt wurden, und C3510a.tlb wurde gelöscht oder nicht auf den Pfad.  
  
```  
// C3510a.idl  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12b")]  
library C3510aLib  
{  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12c")]  
   enum E_C3510  
   {  
      one, two, three  
   };  
};  
```  
  
 Und klicken Sie dann den Quellcode für die zweite Typbibliothek:  
  
```  
// C3510b.idl  
// post-build command: del /f C3510a.tlb  
[uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12e")]  
library C3510bLib  
{  
   importlib ("C3510a.tlb");  
   [uuid("f87070ba-c6d9-405c-a8e4-8cd9ca25c12d")]  
   struct S_C3510 {  
      enum E_C3510 e;  
   };  
};  
```  
  
 Und klicken Sie dann den Clientcode:  
  
```  
// C3510.cpp  
#import "c3510b.tlb" no_registry auto_search   // C3510  
int main() {  
   C3510aLib::S_C4336 ccc;  
}  
```