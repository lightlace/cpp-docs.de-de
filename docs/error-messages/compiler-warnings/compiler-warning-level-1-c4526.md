---
title: Compilerwarnung (Stufe 1) C4526 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4526
dev_langs:
- C++
helpviewer_keywords:
- C4526
ms.assetid: 490f8916-5fdc-4cad-b412-76c3382a5976
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5a38d629d61e16b038701522d4bb27a4de7391d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33282898"
---
# <a name="compiler-warning-level-1-c4526"></a>Compilerwarnung (Stufe 1) C4526
'Funktion': statische Memberfunktion kann nicht virtuelle Funktion, die außer Kraft setzen "virtuelle function'override ignoriert, virtuelle Funktion wird ausgeblendet  
  
 Die statische Memberfunktion erfüllt die Kriterien für die virtuelle Funktion überschreiben, wodurch die Memberfunktion sowohl statische als auch virtuelle.  
  
 Der folgende Code generiert C4526:  
  
```  
// C4526.cpp  
// compile with: /W1 /c  
// C4526 expected  
struct myStruct1 {  
   virtual void __stdcall func( int ) = 0;  
};  
  
struct myStruct2: public myStruct1 {  
   static void __stdcall func( int );  
};  
```  
  
 Im folgenden sind mögliche Korrekturen aufgeführt:  
  
-   Wenn die Funktion wurde der virtuellen Funktion der Basisklasse überschreiben, entfernen Sie den statischen Spezifizierer.  
  
-   Wenn die Funktion eine statische Memberfunktion sein sollte, benennen Sie sie, sodass kein Konflikt mit der virtuellen Basisklasse-Funktion entsteht.