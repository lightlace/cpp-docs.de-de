---
title: Compilerfehler C3163 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3163
dev_langs: C++
helpviewer_keywords: C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4d3cbb5c5c3e8391b3a549fc0c34661dc86b492c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3163"></a>Compilerfehler C3163
'construct': Attribute, die mit der vorherigen Deklaration nicht konsistent.  
  
 Die Attribute, die für die Definition einer angewendet werden in Konflikt mit den Attributen, die eine Deklaration angewendet werden.  
  
 Eine Möglichkeit zum Auflösen von C3163 ist um Attribute für die Vorwärtsdeklaration zu entfernen. Alle Attribute in einer Vorwärtsdeklaration sollte niedriger sein als die Attribute für die Definition oder höchstens gleich.  
  
 Eine mögliche Ursache des Fehlers C3163 umfasst Microsoft Source Code Annotation Language (SAL). Die SAL-Makros nicht erweitern, wenn Sie das Projekt, mithilfe kompiliert der **/ analyze** Flag. Ein Programm, das kompiliert wird ordnungsgemäß heruntergefahren, ohne / analyze möglicherweise C3163 auslösen, wenn Sie versuchen, kompilieren sie mit der / analyze-Option. Weitere Informationen zu SAL, finden Sie unter [SAL-Anmerkungen](../../c-runtime-library/sal-annotations.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird C3163 generiert.  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [SAL-Anmerkungen](../../c-runtime-library/sal-annotations.md)