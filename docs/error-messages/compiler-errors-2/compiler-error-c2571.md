---
title: Compilerfehler C2571 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dea582cf5d1211d57eac94a7f70458a51542ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2571"></a>Compilerfehler C2571
"Function": virtuelle Funktion kann nicht in Union "Union"  
  
 Eine Union wird mit einer virtuellen Funktion deklariert. Sie können eine virtuelle Funktion nur in einer Klasse oder Struktur deklarieren.  Folgende Lösungen möglich:  
  
1.  Ändern Sie die Union in einer Klasse oder Struktur an.  
  
2.  Stellen Sie die Funktion nicht virtuell.  
  
 Im folgende Beispiel wird C2571 generiert:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```