---
title: "Empfehlungen zur Eingabe-/Ausgabebehandlung | Microsoft Docs"
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
  - "Dateibasierte E/A-Optionen"
  - "E/A [C++]"
  - "E/A [C++], Dateibasierte Optionen"
  - "E/A [C++], Optionen"
  - "E/A [MFC], Informationen über E/A"
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Empfehlungen zur Eingabe-/Ausgabebehandlung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ob Sie dateibasierte E\/A verwenden oder nicht, hängt davon ab, wie Sie auf die Fragen in der folgenden Entscheidungsstruktur reagieren:  
  
 **Befinden sich die primären Daten in der Anwendung in einer Datenträgerdatei?**  
  
-   Ja, um die primären Daten befindet sich in einer Datenträgerdatei:  
  
     **Liest die Anwendung die gesamte Datei in den Arbeitsspeicher auf der geöffneten Datei und schreibt die gesamte Datei wieder auf den Datenträger auf Datei\-Abwehr?**  
  
    -   Ja: Dies ist der Dokumentfall standardmäßigen MFC.  Verwendungs **CDocument** Serialisierung.  
  
    -   Nein: Dies ist normalerweise der Fall Transaktion\-basierten Aktualisierung der Datei.  Sie aktualisieren die Datei auf einer ProTransaktionsbasis und benötigen keine **CDocument** Serialisierung.  
  
-   Nein, um die primären Daten befindet sich nicht in einer Datenträgerdatei:  
  
     **Befinden sich die Daten in einer ODBC\-Datenquelle?**  
  
    -   Ja, die Daten befindet sich in einer ODBC\-Datenquelle:  
  
         Datenbankunterstützung der von MFC.  Die Implementierung des Standardanbieters MFC für diesen Fall enthält ein **CDocument**\-Objekt, das ein `CDatabase`\-Objekt speichert, wie im Artikel [Was ist das MFC\-Datenbank\-Programmiermodell?](../data/what-is-the-mfc-database-programming-model-q.md) erläutert.  Die Anwendung auch eine Arbeitsdatei lesen und schreiben \- den Zweck des Anwendungs\-Assistenten "eine Datenbankansicht archivierte und möglicherweise Stütz" Option.  In diesem Fall würden Sie die Serialisierung der Arbeitsdatei verwenden.  
  
    -   Nein, die Daten befindet sich nicht in einer ODBC\-Datenquelle.  
  
         Beispiele aus diesem Fall: die Daten befinden sich in einem NichtODBC DBMS; die Daten werden über einen anderen Mechanismus, wie OLE oder DDE gelesen.  
  
         Verwenden Sie in solchen Fällen die Serialisierung nicht, und die Anwendung verfügt nicht geöffnet und sichert Menüelemente.  Sie sollten dennoch **CDocument** als Heimatstandort verwenden, wie eine Anwendung MFC\-ODBC das Dokument verwendet, um `CRecordset`\-Objekte zu speichern.  Es wird nicht die Standarddatei des Frameworks Serialisierung des offenen\/Abwehrdokuments.  
  
 Um das geöffnete, stellt Speicherungs\- und speichern als Befehle im Menü Datei zu unterstützen, dem Framework Dokumentserialisierung.  Serialisierung liest und schreibt Daten, einschließlich Objekte, die von der Klasse `CObject`, den permanenten Speicher, normalerweise einer Datenträgerdatei abgeleitet werden.  Serialisierung ist einfach und entspricht viele Ihrer Anforderungen, aber es kann in vielen Anwendungen nicht geeignet.  Datenzugriffsanwendungen aktualisieren in der Regel auf Daten einer ProTransaktionsbasis.  Sie aktualisieren die Datensätze, die von der Transaktion anstatt Lesen und Schreiben eine ganze Datendatei sofort beeinflusst werden.  
  
 Weitere Informationen zur Serialisierung, finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## Siehe auch  
 [Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe\/\-ausgabe](../mfc/serialization-serialization-vs-database-input-output.md)