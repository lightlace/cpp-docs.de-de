---
title: "Compilerfehler C3728"
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
  - "C3728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3728"
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerfehler C3728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Ereignis': Das Ereignis hat keine raise\-Methode  
  
 Mithilfe der [\#using](../../preprocessor/hash-using-directive-cpp.md)\-Direktive wurden mit einer Programmiersprache \(z. B. C\#\) erstellte Metadaten eingefügt, die nicht zulassen, dass ein Ereignis außerhalb der definierenden Klasse ausgelöst wird. Ein Visual C\+\+\-Programm mit CLR\-Programmierung hat versucht, das Ereignis auszulösen.  
  
 Um ein Ereignis in einem Programm auszulösen, das in einer Sprache wie C\# entwickelt wurde, muss die Klasse, in der das Ereignis enthalten ist, auch eine öffentliche Methode zur Auslösung des Ereignisses definieren.