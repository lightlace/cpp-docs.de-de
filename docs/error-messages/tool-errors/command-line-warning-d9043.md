---
title: "Befehlszeilenwarnung D9043 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "D9043"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "D9043"
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Befehlszeilenwarnung D9043
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ungültiger Wert 'warning\_level' für 'compiler\_option'; '4999' wird angenommen; Warnungen der Codeanalyse sind keine Warnstufen zugeordnet  
  
## Beispiel  
 Im folgenden Beispiel wird C9043 generiert.  
  
```  
// D9043.cpp  
// compile with: /analyze /w16001  
// D9043 warning expected  
int main() {}  
```