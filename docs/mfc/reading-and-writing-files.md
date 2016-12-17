---
title: "Lesen und Schreiben von Dateien"
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
  - "CFile-Klasse, Objekte"
  - "CFile-Klasse, Lesen und Schreiben von CFile-Objekte"
  - "Beispiele [MFC], Lesen von Dateien"
  - "Beispiele [MFC], Schreiben in Dateien"
  - "Dateien [C++], Lesen"
  - "Dateien [C++], Schreiben in"
  - "MFC [C++], Dateivorgänge"
  - "Lesen von Dateien"
  - "Schreiben in Dateien [C++]"
ms.assetid: cac0c826-ba56-495f-99b3-ce6336f65763
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Lesen und Schreiben von Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie die C\-Laufzeitbibliotheks\-DateiBehandlungsfunktionen verwendet haben, finden MFC\-Lesen und \-Schreiboperationen vertraut aus.  Dieser Artikel beschreibt, direkt lesen und ausgeben direkt auf ein `CFile`\-Objekt schreiben.  Sie können gepufferte Datei\-E\/A mit der Klasse [CArchive](../mfc/reference/carchive-class.md) ausführen.  
  
#### So Lese\- und in die Datei schreiben  
  
1.  Verwenden Sie **Lesen** und **Schreiben**\-Memberfunktionen, um Daten in die Datei zu lesen und zu schreiben.  
  
     \- oder \-  
  
2.  Die `Seek`\-Memberfunktion ist auch für das Wechseln zu einem bestimmten Offset in die Datei verfügbar.  
  
 **Lesen** akzeptiert einen Zeiger auf einen Puffer und die Anzahl von Bytes, die zum Lesen und die tatsächliche Anzahl von Bytes zurück, die gelesen wurden.  Wenn die benötigte Anzahl von Bytes nicht gelesen werden konnte, da dass \(EOF\) erreicht wird, wird die tatsächliche Anzahl der gelesenen Bytes zurückgegeben.  Falls tritt Lesefehler, wird eine Ausnahme ausgelöst auf.  **Schreiben** entspricht **Lesen** ähnlich, aber die Anzahl der Bytes geschrieben wurde nicht zurückgegeben.  Wenn ein Schreibfehler erfolgt, das Schreiben aller Bytes nicht angegeben einschließend, wird eine Ausnahme ausgelöst.  Wenn Sie einen gültigen `CFile`\-Objekt verfügen, können Sie von ihm lesen oder darauf wie im folgenden Beispiel schreiben:  
  
 [!CODE [NVC_MFCFiles#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCFiles#2)]  
  
> [!NOTE]
>  Sie sollten Eingabe\/Ausgabe\-Arbeiten innerhalb eines **try**\/**catch** Ausnahmebehandlungsblocks normalerweise ausführen.  Weitere Informationen finden Sie unter [Ausnahmebehandlung \(MFC\)](../mfc/exception-handling-in-mfc.md).  
  
## Siehe auch  
 [Dateien](../mfc/files-in-mfc.md)