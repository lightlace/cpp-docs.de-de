---
title: "Compilerwarnung (Stufe 4) C4718 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4718"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4718"
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Compilerwarnung (Stufe 4) C4718
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktionsaufruf': Rekursiver Aufruf besitzt keine Nebeneffekte, wird gelöscht  
  
 Eine Funktion enthält einen rekursiven Aufruf, hat aber ansonsten keine Nebeneffekte. Ein Aufruf dieser Funktion wird gelöscht. Die Richtigkeit des Programms ist nicht betroffen, aber die Verhaltensweise. Wenn der Aufruf beibehalten wird, kann dies zu einer Stapelüberlaufausnahme zur Laufzeit führen. Das Löschen des Aufrufs beseitigt diese Möglichkeit.