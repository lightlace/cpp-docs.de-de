---
title: Fehlender Funktionsrumpf oder fehlende Variable | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- function body
- variables, missing
ms.assetid: 1a88d809-b14f-46a4-97c4-3e48beb418f2
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4bac7b2942f9d72674b8092dc7bf64174dd3c349
ms.openlocfilehash: c80a5626e7f674ddca7d44e94aa8ab64c735c81e
ms.contentlocale: de-de
ms.lasthandoff: 04/24/2017

---
# <a name="missing-function-body-or-variable"></a>Fehlender Funktionsrumpf oder fehlende Variable
Klicken Sie mit nur einem Funktionsprototyp der Compiler ohne Fehler fortgesetzt, obwohl der Linker kann keinen Aufruf an eine Adresse nicht aufgelöst werden, da keine Funktionscode oder die Variable reservierte Speicherplatz vorhanden ist. Dieser Fehler wird nicht angezeigt werden, bis Sie einen Aufruf der Funktion erstellen, die der Linker auflösen müssen.  
  
## <a name="example"></a>Beispiel  
 Der Funktionsaufruf in Main wird zum Fehler LNK2019 führen, da der Prototyp kann der Compiler glauben, dass die Funktion vorhanden ist.  Der Linker sucht nach, dass dies nicht der Fall.  
  
```  
// LNK2019_MFBV.cpp  
// LNK2019 expected  
void DoSomething(void);  
int main() {  
   DoSomething();  
}  
```  
  
## <a name="example"></a>Beispiel  
 Stellen Sie in C++ sicher, dass Sie die Implementierung einer bestimmten Funktion für eine Klasse und nicht nur einen Prototyp in der Klassendefinition einschließen. Wenn Sie die Klasse außerhalb der Headerdatei definieren, werden Sie sicherstellen, dass der Name der Klasse vor der Funktion (`Classname::memberfunction`).  
  
```  
// LNK2019_MFBV_2.cpp  
// LNK2019 expected  
struct A {  
   static void Test();  
};  
  
// Should be void A::Test() {}  
void Test() {}  
  
int main() {  
   A AObject;  
   AObject.Test();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Linkertoolfehler LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)
