---
title: "Ausnahmebehandlung in MFC | Microsoft Docs"
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
  - "Nicht ordnungsgemäße Programmausführung [C++]"
  - "Archivausnahmen [C++]"
  - "Assertionen [C++], Ausnahmen verwenden"
  - "Automatisierung [C++], Ausnahmen"
  - "C++-Ausnahmebehandlung, Aktivieren"
  - "C++-Ausnahmebehandlung, MFC-Anwendungen"
  - "C++-Ausnahmebehandlung, Typen"
  - "Klassenbibliotheken [C++], Ausnahmeunterstützung"
  - "DAO [C++], Ausnahmen"
  - "Datenbankausnahmen [C++]"
  - "Fehlerbehandlung [C++], Ausnahmen und"
  - "Fehler [C++], von Assertionen erkannt"
  - "Ausnahmebehandlung [C++], MFC"
  - "Ausnahmemakros [C++]"
  - "Ausnahmen [C++], MFC-Makros und C++Schlüsselwörter"
  - "Funktionsaufrufe, Ergebnisse"
  - "Schlüsselwörter [C++], Ausnahmebehandlung"
  - "Makros [C++], Ausnahmebehandlung"
  - "Makros [C++], MFC-Ausnahmemakros"
  - "Speicher [C++], out_of_memory-Ausnahmen"
  - "MFC [C++], Ausnahmen"
  - "ODBC-Ausnahmen [C++]"
  - "OLE-Ausnahmen [C++], MFC-Ausnahmebehandlung"
  - "out-of-memory-Ausnahmen [C++]"
  - "vordefinierte Ausnahmen [C++]"
  - "Anforderung für nicht unterstützte Dienste"
  - "Ausnahme für die Ressourcenspeicherbelegung"
  - "Ressourcen [C++], Reservieren"
  - "Serialisierung [C++], Ausnahmen"
  - "Windows [C++], Ausnahmen für die Ressourcenspeicherbelegung"
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Ausnahmebehandlung in MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt die Ausnahmebehandlungsmechanismen, die in MFC verfügbar sind.  Zwei Mechanismen sind verfügbar:  
  
-   C\+\+\-Ausnahmen, verfügbar in MFC 3.0 und höher  
  
-   Die MFC\-Ausnahmemakros, das verfügbar in MFC\-Versionen 1.0 und höher  
  
 Wenn Sie eine neue Anwendung mit MFC schreiben, sollten Sie den C\+\+\-Mechanismus verwenden.  Sie können den Makro\-basierten Mechanismus verwenden wenn die Verwendung der vorhandenen Anwendung bereits dieser Mechanismus umfassend.  
  
 Sie können vorhandenen Code bereit konvertieren, um C\+\+\-Ausnahmen anstelle der MFC\-Ausnahmemakros zu verwenden.  Vorteile des Konvertierens des Codes und Richtlinien hierfür werden im Artikel [Ausnahmen: Umwandeln von MFC\-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md) beschrieben.  
  
 Wenn Sie bereits eine Anwendung mit der MFC\-Ausnahmemakros entwickelt haben, können Sie mithilfe dieser Makros im vorhandenen Code weiterhin, bei der Verwendung von C\+\+\-Ausnahmen in Ihrem neuen Code.  Der Artikel [Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) gibt Richtlinien hierfür.  
  
> [!NOTE]
>  So fügen Sie der C\+\+\-Ausnahmebehandlung zu aktivieren, die im Code verarbeitet, ausgewählt aktivieren C\+\+\-Ausnahmen auf der Codegenerierungsseite im Ordner C\/C\+\+ des Dialogfelds [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md) des Projekts oder verwenden die Compileroption \/GX\-.  Der Standardwert ist \/GX \-, deaktiviert der Ausnahmebehandlung.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Wann Ausnahmen verwendet](#_core_when_to_use_exceptions)  
  
-   [MFC\-Ausnahmeunterstützung](#_core_mfc_exception_support)  
  
-   [Weiterführende Themen zu Ausnahmen](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a> Wann Ausnahmen verwendet  
 Drei Kategorien Ergebnisse können auftreten, wenn eine Funktion während der Programmausführung aufgerufen wird: normale Ausführung, fehlerhafte Ausführung oder nicht die normale Ausführung.  Jede Kategorie wird nachfolgend beschrieben.  
  
-   Normale Ausführung  
  
     Die Funktion normalerweise ausführen und beendet werden.  Einige Funktionen geben einem Ergebniscode zum Aufrufer zurück, der das Ergebnis der Funktion angibt.  Die möglichen Ergebniscodes werden ausschließlich für die Fähigkeit definiert und den Bereich möglicher Ergebnissen der Funktion darstellen.  Der Ergebniscode kann Erfolg oder Fehler angeben oder kann einem bestimmten Typ Fehler auch angeben, der innerhalb des Normbereichs die Erwartungen ist.  Beispielsweise kann eine DateiStatusfunktion einem Code zurückgeben, der angibt, dass die Datei nicht vorhanden ist.  Beachten Sie, dass der Begriff "Fehlercode" nicht verwendet wird, da ein Ergebniscode eines vieler erwarteten Ergebnisse darstellt.  
  
-   Fehlerhafte Ausführung  
  
     Der Aufrufer ist, einen Fehler, wenn die Argumente der Funktion übergibt oder ruft die Funktion in einem ungeeigneten Kontext auf.  Diese Situation verursacht einen Fehler, und sollte durch eine Assertion während der Programmentwicklung erkannt werden. \(Weitere Informationen zu Assertionen, finden Sie unter [C\/C\+\+\-Assertionen](../Topic/C-C++%20Assertions.md).\)  
  
-   Nicht normale Ausführung  
  
     Nicht normale Ausführung enthält Situationen, in denen Anforderungen außerhalb des Steuerelements des Programms, wie Arbeitsspeicher oder niedriger E\/A\-Fehler, das Ergebnis der Funktion beeinträchtigen.  Nicht normale Situationen sollten behandelt werden, indem Ausnahmen abfängt und ausgelöst.  
  
 Das Verwenden von Ausnahmen ist für normale Ausführung nicht besonders geeignet.  
  
##  <a name="_core_mfc_exception_support"></a> MFC\-Ausnahme\-Unterstützung  
 Ob Sie die C\+\+\-Ausnahmen direkt verwenden oder die MFC\-Ausnahmemakros verwenden, verwenden Sie [CException Class](../mfc/reference/cexception-class.md) oder `CException` abgeleitete Objekte, die durch das Framework oder von der Anwendung ausgelöst werden.  
  
 Die folgende Tabelle enthält die vordefinierten Ausnahmen an, die von MFC bereitgestellte werden.  
  
|Ausnahmeklasse|Bedeutung|  
|--------------------|---------------|  
|[CMemoryException Class](../mfc/reference/cmemoryexception-class.md)|Mit genügend Arbeitsspeicher|  
|[CFileException Class](../mfc/reference/cfileexception-class.md)|Dateiausnahme|  
|[CArchiveException Class](../mfc/reference/carchiveexception-class.md)|Archiv\-\/Serialisierungsausnahme|  
|[CNotSupportedException Class](../mfc/reference/cnotsupportedexception-class.md)|Antwort an Anforderungen um nicht unterstützten Dienst|  
|[CResourceException Class](../mfc/reference/cresourceexception-class.md)|Windows\-Ressourcenzuordnungsausnahme|  
|[CDaoException Class](../mfc/reference/cdaoexception-class.md)|Datenbankausnahmen \(DAO\-Klassen\)|  
|[CDBException Class](../mfc/reference/cdbexception-class.md)|ODBC\-Klassen Datenbankausnahmen\(\)|  
|[COleException Class](../mfc/reference/coleexception-class.md)|OLE\-Ausnahmen|  
|[COleDispatchException Class](../mfc/reference/coledispatchexception-class.md)|Ausnahmen des gibt \(Automatisierung\)|  
|[CUserException Class](../mfc/reference/cuserexception-class.md)|Ausnahme, die den Benutzer mit einem Meldungsfeld werden, löst generisches [CException Class](../mfc/reference/cexception-class.md) aus|  
  
> [!NOTE]
>  MFC unterstützt C\+\+\-Ausnahmen und die MFC\-Ausnahmemakros.  MFC nicht direkt unterstützt Handler \(SEH\) Windows NT\-strukturierter Ausnahme, wie in [Strukturierte Ausnahmebehandlung](http://msdn.microsoft.com/library/windows/desktop/ms680657) erläutert.  
  
##  <a name="_core_further_reading_about_exceptions"></a> Weiterführende Themen zu Ausnahmen  
 Die folgenden Elemente beschreiben mit der MFC\-Bibliothek für die Ausnahmeübergebung:  
  
-   [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [Ausnahmen: Untersuchen von Ausnahmeinhalten](../mfc/exceptions-examining-exception-contents.md)  
  
-   [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [Ausnahmen: Ausnahmen in eigenen Funktionen auslösen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [Ausnahmen: Datenbankausnahmen](../mfc/exceptions-database-exceptions.md)  
  
-   [Ausnahmen: OLE\-Ausnahmen](../mfc/exceptions-ole-exceptions.md)  
  
 Die folgenden Elemente vergleichen die MFC\-Ausnahmemakros mit den C\+\+\-Ausnahme\-Schlüsselworten und beschreiben, wie Sie den Code anpassen können:  
  
-   [Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [Ausnahmen: Umwandeln von MFC\-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [Ausnahmen: Verwenden von MFC\-Makros und C\+\+\-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## Siehe auch  
 [C\+\+\-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)   
 [Wie behebe ich: Erstellen Sie die My eigenen benutzerdefinierten Ausnahme\-Klassen?](http://go.microsoft.com/fwlink/?LinkId=128045)