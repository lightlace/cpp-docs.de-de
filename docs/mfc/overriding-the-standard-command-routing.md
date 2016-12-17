---
title: "&#220;berschreiben des Standardbefehlsroutings"
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
  - "Befehlsbehandlung, Routingbefehle"
  - "Befehlsrouting, Überschreiben"
  - "MFC, Befehlsrouting"
  - "Überschreiben, Standardbefehlsrouting"
ms.assetid: 872b698a-7432-40c4-9008-68721e8effa5
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berschreiben des Standardbefehlsroutings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In seltenen Fällen, wenn Sie etwas Variante des Standardframeworks implementieren müssen weiterleitend, können Sie diesen überschreiben.  Die Idee ist, das Routing in einer oder mehreren Klassen zu ändern, indem `OnCmdMsg` in diesen Klassen überschrieben wird.  Führen Sie auf:  
  
-   In der Klasse, die die Reihenfolge unterbricht, an einem nicht standardmäßigen Objekt zu übergeben.  
  
-   Im neuen nicht standardmäßigen Objekt oder den Befehlszielen hat sie möglicherweise wiederum Befehle zu.  
  
 Wenn Sie ein neues Objekt in das Routing einfügen, muss die Klasse eine BefehlZielklasse sein.  In Ihren überschreibende Versionen von `OnCmdMsg`, stellen Sie sicher aufzurufen, die Version, die Sie überschreiben.  Siehe die [OnCmdMsg](../Topic/CCmdTarget::OnCmdMsg.md)\-Memberfunktion der Klasse `CCmdTarget` der Klasse in derMFC\-Referenz und in Versionen in solchen Klassen wie `CView` und **CDocument** im angegebenen Quellcode für Beispiele.  
  
## Siehe auch  
 [Wie das Framework einen Handler aufruft](../mfc/how-the-framework-calls-a-handler.md)