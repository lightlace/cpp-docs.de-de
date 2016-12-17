---
title: "Definieren von Makros"
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
helpviewer_keywords: 
  - "Definieren von Makros"
  - "Makros, NMAKE"
  - "NMAKE (Programm), Definieren von Makros"
ms.assetid: 0fc59ec5-5f58-4644-b7da-7b021f7001af
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Definieren von Makros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Makros werden in einer Befehlszeile, einer Befehlsdatei, einem Makefile oder in der Datei Tools.ini definiert.  
  
 In einem Makefile oder der Datei Tools.ini muss sich jede Makrodefinition in einer separaten Zeile befinden und kann nicht mit einem Leerzeichen oder Tabstopp beginnen.  Leerzeichen oder Tabstopps um das Gleichheitszeichen werden ignoriert.  Alle [Zeichen der Zeichenfolge](../build/defining-an-nmake-macro.md) sind literal, einschließlich der sie umgebenden Anführungszeichen sowie eingebetteter Leerzeichen.  
  
 In einer Befehlszeile oder Befehlsdatei werden Argumente von Leerzeichen und Tabstopps getrennt. Daher darf das Gleichheitszeichen nicht von Leerzeichen und Tabstopps umgeben sein.  Wenn `string` eingebettete Leerzeichen oder Tabstopps enthält, wird entweder die Zeichenfolge oder das gesamte Makro in doppelte Anführungszeichen \(**" "**\) eingeschlossen.  
  
## Siehe auch  
 [Definieren eines NMAKE\-Makros](../build/defining-an-nmake-macro.md)