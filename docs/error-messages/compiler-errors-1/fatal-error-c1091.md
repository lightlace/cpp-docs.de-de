---
title: "Schwerwiegender Fehler C1091 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C1091"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1091"
ms.assetid: 812d4201-9154-48b0-b9af-5959c082ca33
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Schwerwiegender Fehler C1091
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit: Die Zeichenfolge überschreitet die Länge um "Länge" Bytes.  
  
 Eine Zeichenfolgekonstante hat die aktuelle Grenze für die Länge von Zeichenfolgen überschritten.  
  
 Teilen Sie ggf. die statische Zeichenfolge in zwei \(oder mehr\) Variablen auf und verwenden Sie [strcpy\_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md), um das Ergebnis im Rahmen der Deklaration oder während der Laufzeit zusammenzuführen.