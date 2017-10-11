---
title: Compilerfehler Fehler C2002 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8f6fc5983a462850581f69ca32dd7c305f9e847
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2002"></a>Compilerfehler Fehler C2002
Ungültige Breitzeichen-Konstante  
  
 Die Mehrbyte-Konstante ist ungültig.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Breitzeichenkonstante enthält mehr Bytes als erwartet.  
  
2.  Der Standardheader STDDEF.h ist nicht enthalten.  
  
3.  Breitzeichen können nicht mit gewöhnlichen Zeichenfolgenliteralen verkettet werden.  
  
4.  Eine Breitzeichenkonstante muss das Zeichen "L" vorangestellt werden:  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Für Microsoft C++ müssen die Argumente einer Präprozessordirektive ASCII sein. Z. B. die Richtlinie `#pragma message(L"string")`, ist ungültig.
