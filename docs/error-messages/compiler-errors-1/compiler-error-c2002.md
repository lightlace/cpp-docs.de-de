---
title: "Compilerfehler C2002"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2002"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2002"
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2002
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültige "breite" Zeichenkonstante  
  
 Die Mehrbyte\-Zeichenkonstante ist nicht zulässig.  
  
### Dieser Fehler kann eine der folgenden Ursachen haben:  
  
1.  Die Breitzeichenkonstante enthält mehr Bytes als erwartet.  
  
2.  Der Standardheader STDDEF.h ist nicht enthalten.  
  
3.  Breitzeichen können nicht mit gewöhnlichen Zeichenfolgenliteralen verkettet werden.  
  
4.  Einer Breitzeichenkonstanten muss das Präfix "L" vorangestellt werden.  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Für Microsoft C\+\+ müssen die Textargumente einer Präprozessordirektive ASCII sein.  Zum Beispiel ist die `#pragma message(L"string")`\-Direktive nicht gültig.