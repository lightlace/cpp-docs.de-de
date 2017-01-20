---
title: "Compilerwarnung (Stufe 1) C4910"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4910"
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4910
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"\<Bezeichner\>": "\_\_declspec\(dllexport\)" und "extern" sind bei einer expliziten Instanziierung nicht miteinander kompatibel.  
  
 Die explizite Vorlageninstanziierung namens *\<Bezeichner\>* wird sowohl durch das `__declspec(dllexport)`\-Schlüsselwort als auch das `extern`\-Schlüsselwort geändert. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)`\-Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern`\-Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.  
  
## Siehe auch  
 [Explizite Instantiierung](../../cpp/explicit-instantiation.md)   
 [dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)