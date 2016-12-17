---
title: "Compilerfehler C2447"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "C2447"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2447"
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
caps.latest.revision: 10
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2447
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"{": Funktionskopf fehlt \- Parameterliste im alten Stil?  
  
 Der Compiler hat eine unerwartete öffnende geschweifte Klammer im globalen Bereich festgestellt.  In den meisten Fällen wird dieser Fehler aufgrund eines falsch formatierten Funktionsheaders, einer falsch platzierten Deklaration oder eines fehlgeleiteten Semikolons verursacht.  Stellen Sie zur Behebung dieses Problems sicher, dass die öffnende Klammer einem ordnungsgemäß formatierten Funktionsheader folgt und ihr weder eine Deklaration noch ein fehlgeleitetes Semikolon vorangeht.  
  
 Dieser Fehler kann auch von einer formalen C\-Argumentliste im alten Stil verursacht werden.  Gestalten Sie zur Behebung dieses Problems die Argumentliste um. Der moderne Stil sieht runde Klammern vor.  
  
 Im folgenden Beispiel wird C2447 generiert:  
  
```  
// C2447.cpp  
int c;  
{}       // C2447  
```