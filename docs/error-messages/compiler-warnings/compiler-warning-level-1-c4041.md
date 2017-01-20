---
title: "Compilerwarnung (Stufe 1) C4041"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "C4041"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4041"
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4041
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compilerlimit : Browserausgabe wird abgebrochen  
  
 Die Browserinformationen haben das Compilerlimit überschritten.  
  
 Diese Warnung kann durch die Kompilierung mit [\/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) \(Browserinformationen einschließlich lokaler Variablen\) verursacht werden.  
  
### So beheben Sie den Fehler \(unterschiedliche Lösungsmöglichkeiten\)  
  
1.  Kompilieren Sie mit \/Fr \(Browserinformationen ohne lokale Variablen\).  
  
2.  Deaktivieren Sie die Browserausgabe \(Kompilieren ohne\/fr oder\/FR\).