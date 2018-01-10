---
title: Compilerwarnung C4485 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4485
dev_langs: C++
helpviewer_keywords: C4485
ms.assetid: a6f2b437-ca93-4dcd-b9cb-df415e10df86
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1289ee1ce2a5f756d7a21f966424007eee704ac1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4485"></a>Compilerwarnung C4485
'Überschreibungsfunktion': Basis Ref-Klassenmethode "Basisklassenfunktion" entspricht, ist jedoch nicht markierte 'new' oder 'override'; "new" (und "virtual") werden angenommen.  
  
 Ein Accessor überschreibt mit oder ohne die `virtual` -Schlüsselwort, eine Basisklasse Accessor-Funktion, aber die `override` oder `new` Spezifizierer war nicht Teil der überschreibenden Funktionssignatur. Hinzufügen der `new` oder `override` Spezifizierer, um diese Warnung zu beheben.  
  
 Finden Sie unter [überschreiben](../../windows/override-cpp-component-extensions.md) und [new (neuer Slot in Vtable)](../../windows/new-new-slot-in-vtable-cpp-component-extensions.md) für Weitere Informationen.  
  
 C4485 wird immer als Fehler ausgegeben. Verwenden der [Warnung](../../preprocessor/warning.md) -Pragma, um C4485 zu unterdrücken.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird C4485 generiert:  
  
```  
// C4485.cpp  
// compile with: /clr  
delegate void Del();  
  
ref struct A {  
   virtual event Del ^E;  
};  
  
ref struct B : A {  
   virtual event Del ^E;   // C4485  
};  
  
ref struct C : B {  
   virtual event Del ^E {  
      void raise() override {}  
      void add(Del ^) override {}  
      void remove(Del^) override {}  
   }  
};  
```