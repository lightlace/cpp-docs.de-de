---
title: Compilerfehler C2396 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2396
dev_langs:
- C++
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3cabcb0acf6f9b0a476df35de887fc3c9e0efb01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2396"></a>Compilerfehler C2396
' your_type '': CLR oder WinRT benutzerdefinierte Konvertierung Functionnot gültig. Muss die Konvertierung von oder zu ausführen: 'T^', 'T^%', 'T^&', wobei T = 'Ihr_Typ' ist  
  
 Eine Konvertierungsfunktion in einem Windows-Runtime- oder verwalteten Typ wies nicht einmal einen Parameter auf, dessen Typ dem Typ entspricht, der die Konvertierungsfunktion aufweist.  
  
 Im folgenden Beispiel wird C2396 generiert und gezeigt, wie Sie diesen Fehler beheben:  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```