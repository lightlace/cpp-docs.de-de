---
title: "Compilerfehler C3050 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3050"
ms.assetid: ee090a0b-29cc-4215-a2f9-d82af79b8e82
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerfehler C3050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Typ1': Eine Verweisklasse kann nicht von 'Typ1' erben.  
  
 `System::ValueType` kann keine Basisklasse für einen Verweistyp sein.  
  
 Im folgenden Beispiel wird C3050 generiert:  
  
```  
// C3050.cpp // compile with: /clr /LD ref struct X : System::ValueType {};   // C3050 ref struct Y {};   // OK  
```