---
title: "Schwerwiegender Fehler C1047"
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
  - "C1047"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1047"
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1047
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Objekt\- oder Bibliotheksdatei 'datei' wurde mit einem älteren Compiler als andere Objekte erstellt. Erstellen Sie die alten Objekte und Bibliotheken neu.  
  
 C1047 wird ausgelöst, wenn Objektdateien oder Bibliotheken, die mit **\/LTCG** erstellt wurden, miteinander verknüpft werden, die Objektdateien oder Bibliotheken aber mit verschiedenen Versionen des Visual C\+\+\-Toolsets erstellt wurden.  
  
 Dies kann auftreten, wenn Sie beginnen, eine neue Compilerversion zu verwenden, für vorhandene Objektdateien oder Bibliotheken aber keine Neuerstellung von Grund auf ausführen.  
  
 Um Fehler C1047 zu beheben, erstellen Sie alle Objektdateien und Bibliotheken neu.