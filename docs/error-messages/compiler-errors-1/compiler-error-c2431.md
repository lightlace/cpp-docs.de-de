---
title: "Compilerfehler C2431 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2431"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2431"
ms.assetid: 88a5b648-c89f-47d1-a20e-63231ab4f0f7
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2431
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unzulässiges Indexregister in 'Bezeichner'  
  
 Das ESP\-Register wurde skaliert bzw. sowohl als Index\- als auch als Basisregister verwendet.  Gemäß der SIB\-Codierung für den x86\-Prozessor ist beides unzulässig.  
  
 Im folgenden Beispiel wird C2431 generiert:  
  
```  
// C2431.cpp  
// processor: x86  
int main() {  
   _asm mov ax, [ESI + 2*ESP]   // C2431  
   _asm mov ax, [esp + esp]   // C2431  
}  
```