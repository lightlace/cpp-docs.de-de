---
title: "Compilerfehler C2708"
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
  - "C2708"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2708"
ms.assetid: d52d3088-1141-42f4-829c-74755a7fcc3a
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C2708
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Die aktuelle Parameterlänge in Bytes unterscheidet sich vom vorherigen Aufruf oder Verweis  
  
 Vor einer [\_\_stdcall](../../cpp/stdcall.md)\-Funktion muss ein Prototyp stehen.  Andernfalls wird der erste Aufruf der Funktion vom Compiler als Prototyp gedeutet. Wenn der Compiler dann einen nicht übereinstimmenden Aufruf findet, tritt dieser Fehler auf.  
  
 Um dieses Problem zu beheben, fügen Sie einen Funktionsprototyp hinzu.