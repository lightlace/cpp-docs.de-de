---
title: "Speicherung von Adressen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Adressen [C++], Speicherung von"
  - "Speicherung [C++], Adressen"
ms.assetid: 423b2402-b847-4788-ad70-943b7c9c5c8b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Speicherung von Adressen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Menge des erforderlichen Arbeitsspeichers für eine Adresse und die Bedeutung der Adresse hängen von der Implementierung des Compilers ab.  Für Zeiger auf verschiedene Typen kann nicht garantiert werden, dass sie die gleiche Länge haben.  Daher ist **sizeof\(char \*\)** nicht unbedingt gleich **sizeof\(int \*\)**.  
  
 **Microsoft\-spezifisch**  
  
 Für den Microsoft C\-Compiler ist **sizeof\(char \*\)** gleich **sizeof\(int \*\)**.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Zeigerdeklarationen](../c-language/pointer-declarations.md)