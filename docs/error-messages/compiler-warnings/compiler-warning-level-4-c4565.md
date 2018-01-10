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
ms.workload: cplusplus
ms.openlocfilehash: b89da26312c68bc76d23fc829a14f17db3d601b8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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