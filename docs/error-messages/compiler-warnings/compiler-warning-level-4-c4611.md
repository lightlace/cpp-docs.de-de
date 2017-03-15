---
title: "Compilerwarnung (Stufe 4) C4611 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4611"
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilerwarnung (Stufe 4) C4611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Interaktion zwischen 'Funktion' und C\+\+\-Objektlöschung ist nicht portabel  
  
 Funktionen, die **catch** beinhalten, unterstützen auf einigen Plattformen u. U. keine C\+\+\-Semantik für die Objektlöschung, wenn sie außerhalb des Gültigkeitsbereichs liegen.  
  
 Um unerwartetes Verhalten zu vermeiden, sollten Sie **catch** möglichst nicht in Funktionen verwenden, die Konstruktoren und Destruktoren besitzen.  
  
 Diese Warnung wird nur einmal ausgegeben; siehe [pragma\-Warning](../../preprocessor/warning.md).