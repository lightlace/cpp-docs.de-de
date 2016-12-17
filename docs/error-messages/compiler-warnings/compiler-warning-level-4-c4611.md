---
title: "Compilerwarnung (Stufe 4) C4611"
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
  - "C4611"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4611"
ms.assetid: bd90d0a6-75f9-4e97-968d-dda6773e9fd8
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 4) C4611
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Interaktion zwischen 'Funktion' und C\+\+\-Objektlöschung ist nicht portabel  
  
 Funktionen, die **catch** beinhalten, unterstützen auf einigen Plattformen u. U. keine C\+\+\-Semantik für die Objektlöschung, wenn sie außerhalb des Gültigkeitsbereichs liegen.  
  
 Um unerwartetes Verhalten zu vermeiden, sollten Sie **catch** möglichst nicht in Funktionen verwenden, die Konstruktoren und Destruktoren besitzen.  
  
 Diese Warnung wird nur einmal ausgegeben; siehe [pragma\-Warning](../../preprocessor/warning.md).