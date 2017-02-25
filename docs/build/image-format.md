---
title: "Bildformat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 3ca3654b-42fe-4253-9f2e-723644041aa0
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Bildformat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das ausführbare Bildformat ist PE32\+.  Die Größe ausführbarer Bilder \(DLLs und EXEs\) ist auf 2 Gigabyte begrenzt. Eine relative Adressierung mit einer 32\-Bit\-Verschiebung kann somit verwendet werden, um statische Bilddaten zu adressieren.  Diese Daten enthalten die Importadressentabelle, Zeichenfolgekonstanten, statische globale Daten usw.  
  
## Siehe auch  
 [x64\-Softwarekonventionen](../build/x64-software-conventions.md)