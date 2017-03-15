---
title: "Compilerfehler C2570 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2570"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2570"
ms.assetid: d65d0b32-2fac-464a-bcdf-0ebcedf3bf32
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C2570
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Union kann keine Basisklasse haben  
  
 Eine Union leitet von einer Klasse, Struktur oder einer anderen Union ab.  Dies ist nicht zulässig.  Deklarieren Sie den abgeleiteten Typ stattdessen als Klasse oder Struktur.  
  
 Im folgenden Beispiel wird C2570 generiert:  
  
```  
// C2570.cpp  
// compile with: /c  
class base {};  
union hasPubBase : public base {};   // C2570  
union hasNoBase {};   // OK  
```