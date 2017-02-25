---
title: "Ausnahmen: Untersuchen von Ausnahmeinhalten | Microsoft Docs"
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
  - "catch-Blöcke, MFC-Funktionsausnahmen"
  - "CException-Klasse, Klassenausnahmen"
  - "Ausnahmebehandlung, MFC"
  - "Auslösen von Ausnahmen, Ausnahmeinhalte"
  - "try-catch-Ausnahmebehandlung, Ausnahmeinhalte"
  - "try-catch-Ausnahmebehandlung, MFC-Funktionsausnahmen"
ms.assetid: dfda4782-b969-4f60-b867-cc204ea7f33a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Ausnahmen: Untersuchen von Ausnahmeinhalten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obwohl das Argument **catch** eines Blocks nahezu beliebigen Datentyp haben kann, lösen die MFC\-Funktionen Ausnahmen von Typen aus, die von der `CException`\- Klasse abgeleitet werden.  Um eine Ausnahme abfangen, die von einer MFC\-Funktion dann ausgelöst wird schreiben Sie einen **catch**\-Block dessen Argument ein Zeiger auf ein `CException`\-Objekt ist \(oder einem Objekt abgeleitet von `CException`, wie `CMemoryException`\).  Abhängig vom genauen Ausnahmetyp, können Sie die Datenmember des Ausnahmeobjekts an um über die genaue Ursache der Ausnahme überprüfen.  
  
 Beispielsweise verfügt der `CFileException` den Typ `m_cause`, der Datenmember einen Aufzählungstyp enthält, der die Ursache der Dateiausnahme angibt.  Beispiele der möglichen Werte sind **CFileException::fileNotFound** und **CFileException::readOnly**.  
  
 Das folgende Beispiel zeigt, wie der Inhalt von `CFileException` überprüft.  Andere Ausnahmetypen können auf ähnliche Weise überprüft werden.  
  
 [!CODE [NVC_MFCExceptions#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCExceptions#13)]  
  
 Weitere Informationen finden Sie unter [Ausnahmen: Freigabe von Objekten in den Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md) und [Ausnahmen: Ausnahmen abfangen und Löschen](../mfc/exceptions-catching-and-deleting-exceptions.md).  
  
## Siehe auch  
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)