---
title: Compilerwarnung (Stufe 4) C4565 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4565
dev_langs: C++
helpviewer_keywords: C4565
ms.assetid: a71f1341-a4a1-4060-ad1e-9322531883ed
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2cbe5e8aecd8863f0b3ba092b8d199c1032ce157
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4565"></a>Compilerwarnung (Stufe 4) C4565
'Funktion': Neudefinition; Das Symbol wurde zuvor mit __declspec(Modifizierer) deklariert.  
  
 Ein Symbol wurde neu definiert oder erneut deklariert, und die zweite Definition oder Deklaration, im Gegensatz zu den ersten Definition oder Deklaration verfügte nicht über eine `__declspec` Modifizierer (***Modifizierer***). Diese Warnung dient nur zu Informationszwecken. Um diese Warnung zu beheben, löschen Sie eine der Definitionen.  
  
 Im folgenden Beispiel wird C4565 generiert:  
  
```  
// C4565.cpp  
// compile with: /W4 /LD  
__declspec(noalias) void f();  
void f();   // C4565  
```