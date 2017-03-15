---
title: "Schwerwiegender Fehler C1854 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1854"
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Schwerwiegender Fehler C1854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Überschreiben der Informationen, die bei der Erstellung der vorkompilierten Headerdatei in folgender Objektdatei formatiert wurden: 'Datei'  
  
 Die **\/Yu**\-Option \(Vorkompilierten Header verwenden\) wurde festgelegt, nachdem die **\/Yc**\-Option \(Vorkompilierten Header erstellen\) für dieselbe Datei angegeben wurde.  Bei einigen Deklarationen \(z. B. solchen mit `__declspec` `dllexport`\) ist diese Vorgehensweise nicht zulässig.