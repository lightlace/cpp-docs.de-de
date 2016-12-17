---
title: "Ausnahmen: Ausnahmen in Konstruktoren"
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
  - "Konstruktoren [C++], Ausnahmen"
  - "Ausnahmen, in Konstruktoren"
  - "Auslösen von Ausnahmen, in Konstruktoren"
ms.assetid: a78eae5a-5821-4b27-9478-1436320ed1e1
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Ausnahmen: Ausnahmen in Konstruktoren
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie eine Ausnahme in einem Konstruktor auslösen, bereinigen, welche Objekte und Speicherbelegungen Sie vor dem Auslösen der Ausnahme ausgeführt haben, wie in [Ausnahmen: Auslösen von Ausnahmen aus den eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md) erläutert.  
  
 Wenn eine Ausnahme in einem Konstruktor ausgelöst wurde, ist der Speicher für das Objekt selbst bereits zugeordnet wurde, bis der Konstruktor aufgerufen wird.  Daher gibt der Compiler automatisch den Speicher frei, der vom Objekt belegt wird, nachdem die Ausnahme ausgelöst.  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Freigabe von Objekten in den Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)