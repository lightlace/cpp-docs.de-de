---
title: "Compilerwarnung (Stufe 1) C4445 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4445"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4445"
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilerwarnung (Stufe 1) C4445
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Funktion' : Eine virtuelle Methode kann in einem WinRT\- oder verwalteten Typ nicht privat sein.  
  
 Wenn eine virtuelle Funktion privat ist, kann über einen abgeleiteten Typ nicht auf diese zugegriffen werden.  Um diesen Fehler zu beheben, ändern Sie den Zugriff auf die virtuelle Memberfunktion in „Protected“ oder „Public“.