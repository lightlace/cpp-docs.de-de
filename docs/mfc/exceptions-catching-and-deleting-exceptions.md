---
title: "Ausnahmen: Abfangen und L&#246;schen von Ausnahmen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AND_CATCH-Makro"
  - "catch-Blöcke, Abfangen und Löschen von Ausnahmen"
  - "Ausnahmebehandlung, Abfangen und Löschen von Ausnahmen"
  - "Ausnahmen, Löschen"
  - "Ausführung, Rückgabe von innerhalb des Erfassungsblocks"
  - "try-catch-Ausnahmebehandlung, Abfangen und Löschen von Ausnahmen"
ms.assetid: 7c233ff0-89de-4de0-a68a-9e9cdb164311
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausnahmen: Abfangen und L&#246;schen von Ausnahmen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgenden Anweisungen und Beispiele zeigen, wie Ausnahmen abfängt und gelöscht werden.  Weitere Informationen zu **try** finden, **catch** und `throw`, Schlüsselwörter [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md).  
  
 Ausnahmehandler die müssen Ausnahmeobjekte löschen, die es verarbeiten, da Fehler, die Ausnahme zu löschen einen Speicherverlust verursacht, wenn dieser Code eine Ausnahme abgefangen.  
  
 Das **catch**\-Block müssen Ausnahmen löschen, wenn:  
  
-   Der **catch**\-Block wird eine neue Ausnahme aus.  
  
     Natürlich dürfen Sie die Ausnahme nicht löschen, wenn Sie die gleiche Ausnahme erneut auslösen:  
  
     [!CODE [NVC_MFCExceptions#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#3)]  
  
-   Ausführungsrückgaben aus dem **catch**\-Block.  
  
> [!NOTE]
>  Wenn Sie das `CException` löschen, verwenden Sie die **Löschen**\-Memberfunktion, um die Ausnahme zu löschen.  Verwenden Sie nicht das **löschen**\-Schlüsselwort, da er fehlschlägt kann, wenn die Ausnahme nicht im Heap befindet.  
  
#### Um Ausnahmen abfangen und löschen  
  
1.  Verwenden Sie das **try**\-Schlüsselwort, um einen Block **try** zu installieren.  Führen Sie alle Programmanweisungen aus, die möglicherweise eine Ausnahme innerhalb eines **try**\-Blocks ausgelöst hat.  
  
     Verwenden Sie das **catch**\-Schlüsselwort, um einen Block **catch** zu installieren.  Platzausnahmebehandlungscode in einem **catch**\-Block.  Der Code im Block **catch** wird nur ausgeführt, wenn der Code innerhalb des **try**\-Blocks eine Ausnahme des Typs ausgelöst, der in der **catch**\-Anweisung angegeben wird.  
  
     Das folgende Skelett zeigt, wie **try** und **catch** werden Blöcke normalerweise angeordnet werden:  
  
     [!CODE [NVC_MFCExceptions#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#4)]  
  
     Wenn eine Ausnahme ausgelöst wird, die Steuerung dem ersten **catch**\-Block, dessen AusnahmeDeklaration den Ausnahmetyp übereinstimmt.  Sie können verschiedene Typen von Ausnahmen mit sequenziellen **catch** Blöcken selektiv behandeln, wie unten aufgeführt:  
  
     [!CODE [NVC_MFCExceptions#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#5)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Konvertieren von MFC\-Ausnahme\-Makros](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)