---
title: "Compilerwarnung (Stufe 1) C4041 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4041"
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 1) C4041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit : Browserausgabe wird abgebrochen  
  
 Die Browserinformationen haben das Compilerlimit überschritten.  
  
 Diese Warnung kann durch die Kompilierung mit [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) \(Browserinformationen einschließlich lokaler Variablen\) verursacht werden.  
  
### So beheben Sie den Fehler \(unterschiedliche Lösungsmöglichkeiten\)  
  
1.  Kompilieren Sie mit \/Fr \(Browserinformationen ohne lokale Variablen\).  
  
2.  Deaktivieren Sie die Browserausgabe \(Kompilieren ohne\/fr oder\/FR\).