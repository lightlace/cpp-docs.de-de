---
title: "Compilerfehler C2790"
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
  - "C2790"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2790"
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
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