---
title: "Compilerwarnung (Stufe 2) C4099 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4099"
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
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