---
title: Compilerfehler C3163 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3163
dev_langs:
- C++
helpviewer_keywords:
- C3163
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 95fb254036d2883b6efe6b81bda54864d533c2a8
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

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
