---
title: "Compilerwarnung (Stufe 2) C4099"
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
  - "C4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4099"
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 2) C4099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Geben Sie den zuerst unter Verwendung von 'Objekttyp1' und jetzt unter Verwendung von 'Objekttyp2' gesehenen Namen ein  
  
 Ein als Struktur deklariertes Objekt wird als Klasse definiert, oder ein als Klasse deklariertes Objekt wird als Struktur definiert.  Der Compiler verwendet den in der Definition festgelegten Typ.  
  
## Beispiel  
 Im folgenden Beispiel wird C4099 generiert.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```