---
title: "Compilerfehler C2790 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2790"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2790"
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2790
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'super': Dieses Schlüsselwort kann nur im Text der Klassenmemberfunktion verwendet werden  
  
 Diese Fehlermeldung wird ausgegeben, sobald der Benutzer versucht, das Schlüsselwort [super](../../cpp/super.md) außerhalb des Kontextes einer Memberfunktion zu verwenden.  
  
 Im folgenden Beispiel wird C2790 generiert:  
  
```  
// C2790.cpp  
void f() {  
   __super::g();   // C2790  
}  
```