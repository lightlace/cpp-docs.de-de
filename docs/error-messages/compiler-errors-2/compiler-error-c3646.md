---
title: Compilerfehler C3646 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3646
dev_langs: C++
helpviewer_keywords: C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6dc0c10874854c3b7c4da2fdd49d4ee575c917d9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3646"></a>Compilerfehler C3646
"Spezifizierer": Unbekannte Überschreibungsspezifizierer  
  
 Der Compiler hat ein Token gefunden, Position, in dem sie ein Überschreibungsspezifizierer wurde erwartet, aber das Token wurde nicht vom Compiler erkannt.  
  
 Weitere Informationen finden Sie unter [Überschreibungsspezifizierer](../../windows/override-specifiers-cpp-component-extensions.md).  
  
 Im folgende Beispiel wird C3646 generiert:  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```