---
title: Compilerfehler Fehler C2002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 01124fc839d6e788ff2dccae325f01f7d4337f5d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164865"
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