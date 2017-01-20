---
title: "Bildformat"
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
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Bildformat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das ausführbare Bildformat ist PE32\+.  Die Größe ausführbarer Bilder \(DLLs und EXEs\) ist auf 2 Gigabyte begrenzt. Eine relative Adressierung mit einer 32\-Bit\-Verschiebung kann somit verwendet werden, um statische Bilddaten zu adressieren.  Diese Daten enthalten die Importadressentabelle, Zeichenfolgekonstanten, statische globale Daten usw.  
  
## Siehe auch  
 [x64\-Softwarekonventionen](../build/x64-software-conventions.md)