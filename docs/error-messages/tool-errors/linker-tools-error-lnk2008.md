---
title: "Linkertoolfehler LNK2008"
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
  - "LNK2008"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2008"
ms.assetid: bbcd83c5-c8ae-439e-a033-63643a5bb373
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2008
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fixup\-Ziel ist nicht als 'Symbolname' ausgerichtet  
  
 LINK hat ein Fixup\-Ziel in der Objektdatei gefunden, das nicht ordnungsgemäß ausgerichtet war.  
  
 Dieser Fehler kann durch eine benutzerdefinierte Ausrichtung \(z. B. \#pragma [pack](../../preprocessor/pack.md)\), einen [align](../../cpp/align-cpp.md)\-Modifizierer oder durch das Verwenden von Assemblercode verursacht werden, wenn dieser Code die Abschnittsausrichtung verändert.  
  
 Wenn keiner der genannten Fälle auf Ihren Code zutrifft, kann auch ein Compilerfehler vorliegen.