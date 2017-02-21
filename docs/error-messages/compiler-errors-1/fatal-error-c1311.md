---
title: "Schwerwiegender Fehler C1311 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1311"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1311"
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Schwerwiegender Fehler C1311
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Das COFF\-Format kann 'var' mit 'Anzahl' Byte\(s\) einer Adresse nicht statisch initialisieren  
  
 Eine Adresse, deren Wert zur Kompilierungszeit nicht bekannt ist, kann keiner Variable statisch zugewiesen werden, deren Typ über einen Speicher mit weniger als 4 Bytes verfügt.  
  
 Dieser Fehler kann in Code auftreten, der ansonsten C\+\+\-gültig ist.  
  
 Das folgende Beispiel zeigt eine Bedingung, die zu C1311 führen kann.  
  
```  
char c = (char)"Hello, world";   // C1311  
char *d = (char*)"Hello, world";   // OK  
```