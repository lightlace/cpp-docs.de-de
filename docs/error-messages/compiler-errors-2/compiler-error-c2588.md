---
title: "Compilerfehler C2588 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2588"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2588"
ms.assetid: 19a0cabd-ca13-44a5-9be3-ee676abf9bc4
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerfehler C2588
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::~Bezeichner': Ungültiger globaler Destruktor  
  
 Der Destruktor wurde nicht für eine Klasse, Struktur oder Union definiert.  Dies ist nicht zulässig.  
  
 Auf der linken Seite des Bereichsauflösungsoperators \(`::`\) fehlt der Name einer Klasse, Struktur oder Union.  
  
 Im folgenden Beispiel wird C2588 generiert:  
  
```  
// C2588.cpp  
~F();   // C2588  
```