---
title: "Compilerfehler C2430 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2430"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2430"
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2430
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mehrere Indexregister in 'Bezeichner'  
  
 Es wurde mehr als ein Register skaliert.  Der Compiler unterstützt zwar das skalierte Indizieren, es kann jedoch jeweils nur ein Register skaliert werden.  
  
## Beispiel  
 Im folgenden Beispiel wird C2430 generiert.  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```