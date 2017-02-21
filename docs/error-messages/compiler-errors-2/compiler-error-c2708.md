---
title: "Compilerfehler C2708 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2708"
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerfehler C2708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Die aktuelle Parameterlänge in Bytes unterscheidet sich vom vorherigen Aufruf oder Verweis  
  
 Vor einer [\_\_stdcall](../../cpp/stdcall.md)\-Funktion muss ein Prototyp stehen.  Andernfalls wird der erste Aufruf der Funktion vom Compiler als Prototyp gedeutet. Wenn der Compiler dann einen nicht übereinstimmenden Aufruf findet, tritt dieser Fehler auf.  
  
 Um dieses Problem zu beheben, fügen Sie einen Funktionsprototyp hinzu.