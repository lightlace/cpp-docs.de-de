---
title: "Arbeiten mit Importbibliotheken und Exportdateien"
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
  - "Exportdateien"
  - "Importbibliotheken"
  - "Importbibliotheken, Erstellen"
  - "LIB [C++], /DEF-Option"
  - "LIB [C++], Importbibliotheken und Exportdateien"
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Arbeiten mit Importbibliotheken und Exportdateien
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Sie können LIB mit der **\/DEF**\-Option verwenden, um eine Importbibliothek und eine Exportdatei zu erstellen.  **LINK** verwendet die Exportdatei, um ein Programm zu erstellen, das Exporte \(in der Regel eine DLL \(Dynamic Link Library\)\) enthält, und die Importbibliothek, um Verweise auf diese Exporte in anderen Programmen aufzulösen.  
  
 Wenn Sie die Importbibliothek in einem vorherigen Schritt erstellen, muss vor der Erstellung der DLL derselbe Satz von Objektdateien zur Erstellung der DLL übergeben werden wie bei der Erstellung der Importbibliothek.  
  
 In den meisten Fällen müssen Importbibliotheken nicht mithilfe von LIB erstellt werden.  Beim Verknüpfen eines Programms, das Exporte enthält \(entweder eine ausführbare Datei oder eine DLL\), erstellt **LINK** automatisch eine Importbibliothek, in der die Exporte beschrieben werden.  Wenn Sie später ein Programm verknüpfen, das Verweise auf diese Exporte enthält, geben Sie einfach die Importbibliothek an.  
  
 Wenn jedoch eine DLL in ein Programm exportiert, aus dem die DLL auch direkt oder indirekt importiert, müssen Sie eine dieser Importbibliotheken unter Verwendung von LIB erstellen.  Beim Erstellen einer Importbibliothek erstellt LIB auch eine Exportdatei.  Diese Exportdatei müssen Sie verwenden, wenn Sie eine der DLLs verknüpfen.  
  
## Siehe auch  
 [LIB\-Referenz](../../build/reference/lib-reference.md)