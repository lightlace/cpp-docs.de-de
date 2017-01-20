---
title: "Schwerwiegender Fehler C1310"
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
  - "C1310"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1310"
ms.assetid: ac48aa51-8023-42fe-b844-3f8bf228fbef
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1310
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Profilgesteuerte Optimierungen sind bei OpenMP nicht verfügbar.  
  
 Sie sind nicht in der Lage, ein Modul mit [\/LTCG: PGI](../../build/reference/ltcg-link-time-code-generation.md) zu verknüpfen, das mit [\/GL](../../build/reference/gl-whole-program-optimization.md) kompiliert wurde.  
  
 Das folgende Beispiel generiert C1310:  
  
```  
// C1310.cpp // compile with: /openmp /GL /link /LTCG:PGI // C1310 expected int main() { int i = 0, j = 10; #pragma omp parallel { #pragma omp for for (i = 0; i < 0; i++) --j; } }  
```