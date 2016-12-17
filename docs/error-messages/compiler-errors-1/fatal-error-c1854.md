---
title: "Schwerwiegender Fehler C1854"
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
  - "C1854"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1854"
ms.assetid: 8c21a9cc-1737-475c-9e57-8725cd8937c1
caps.latest.revision: 6
caps.handback.revision: "6"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1854
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fehler beim Überschreiben der Informationen, die bei der Erstellung der vorkompilierten Headerdatei in folgender Objektdatei formatiert wurden: 'Datei'  
  
 Die **\/Yu**\-Option \(Vorkompilierten Header verwenden\) wurde festgelegt, nachdem die **\/Yc**\-Option \(Vorkompilierten Header erstellen\) für dieselbe Datei angegeben wurde.  Bei einigen Deklarationen \(z. B. solchen mit `__declspec` `dllexport`\) ist diese Vorgehensweise nicht zulässig.