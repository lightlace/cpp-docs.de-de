---
title: Ausnahmebehandlung in MFC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DAO [MFC], exceptions
- assertions [MFC], When to use exceptions
- exception handling [MFC], MFC
- resource allocation exception
- resources [MFC], allocating
- keywords [MFC], exception handling
- errors [MFC], detected by assertions
- ODBC exceptions [MFC]
- serialization [MFC], exceptions
- Automation [MFC], exceptions
- exception macros [MFC]
- predefined exceptions [MFC]
- C++ exception handling [MFC], enabling
- C++ exception handling [MFC], MFC applications
- requests for unsupported services [MFC]
- database exceptions [MFC]
- archive exceptions [MFC]
- MFC, exceptions
- C++ exception handling [MFC], types of
- macros [MFC], exception handling
- abnormal program execution [MFC]
- OLE exceptions [MFC], MFC exception handling
- error handling [MFC], exceptions and
- class libraries [MFC], exception support
- exceptions [MFC], MFC macros vs. C++ keywords
- memory [MFC], out-of-memory exceptions
- Windows [MFC], resource allocation exceptions
- macros [MFC], MFC exception macros
- function calls [MFC], results
- out-of-memory exceptions [MFC]
ms.assetid: 0926627d-2ba7-44a6-babe-d851a4a2517c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0792ddf067f6289d612a9adb0c8ffeaf8e554ed6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="exception-handling-in-mfc"></a>Ausnahmebehandlung in MFC
Dieser Artikel erläutert die Ausnahmebehandlungsmechanismen in MFC verfügbar. Es stehen zwei Mechanismen:  
  
-   C++-Ausnahmen, die in MFC-Version 3.0 und höher verfügbar  
  
-   Die MFC-Ausnahmemakros in MFC-Versionen 1.0 und höher verfügbar  
  
 Wenn Sie eine neue Anwendung mit MFC schreiben, sollten Sie den C++-Mechanismus verwenden. Wenn die vorhandene Anwendung bereits diesen Mechanismus sehr häufig verwendet, können Sie das Makro basierenden Mechanismus.  
  
 Sie können ohne weiteres vorhandenen Code zum Verwenden von C++-Ausnahmen anstelle der MFC-Ausnahmemakros konvertieren. Vorteile der Konvertierung von Code sowie Richtlinien für die auf diese Weise werden im Artikel beschriebenen [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md).  
  
 Wenn Sie bereits eine Anwendung mit der MFC-Ausnahmemakros entwickelt haben, können Sie weiterhin, verwenden diese Makros in vorhandenem Code, bei der Verwendung von C++-Ausnahmen im neuen Code. Der Artikel [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) durch Richtlinien auf diese Weise erhalten.  
  
> [!NOTE]
>  Um C++-Ausnahmebehandlung im Code zu aktivieren, wählen Sie auf den C++-Ausnahmen aktivieren, auf der Seite Codegenerierung im C/C++-Ordner des Projekts auf der [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md) (Dialogfeld), oder verwenden Sie die/GX (Compileroption). Der Standardwert ist /GX-, wodurch Ausnahmebehandlung deaktiviert.  
  
 In diesem Artikel werden die folgenden Themen behandelt:  
  
-   [Ausnahmen verwenden](#_core_when_to_use_exceptions)  
  
-   [Unterstützung für MFC-Ausnahme](#_core_mfc_exception_support)  
  
-   [Weitere Informationen zu Ausnahmen](#_core_further_reading_about_exceptions)  
  
##  <a name="_core_when_to_use_exceptions"></a> Ausnahmen verwenden  
 Drei Kategorien von Ergebnissen können auftreten, wenn eine Funktion, die während der Ausführung des Programms aufgerufen wird: normale Ausführung, fehlerhafte Ausführung oder nicht ordnungsgemäße Ausführung. Jede Kategorie wird im folgenden beschrieben.  
  
-   Normale Ausführung  
  
     Die Funktion möglicherweise normal ausgeführt und zurückgegeben. Einige Funktionen geben einen Ergebniscode zurück, an den Aufrufer, der das Ergebnis der Funktion angibt. Die möglichen Ergebniscodes sind ausschließlich für die Funktion definiert und den Bereich von möglichen Ergebnissen der Funktion darstellen. Der Ergebniscode kann auf Erfolg oder Fehler hin oder bedeutet kann auch eine bestimmte Art von Fehler, der in den normalen Wertebereich erwartet wird. Beispielsweise kann eine Dateistatus Funktion einen Code zurückgeben, der angibt, dass die Datei nicht vorhanden ist. Beachten Sie, dass der Begriff "Fehlercode:" nicht verwendet wird, da ein Ergebniscode eines von vielen erwarteten Ergebnissen darstellt.  
  
-   Fehlerhafte Ausführung  
  
     Der Aufrufer einige Fehler bei der Übergabe von Argumenten an die Funktion macht oder die Funktion in einem ungeeigneten Kontext aufruft. Diese Situation tritt ein Fehler, und es sollte eine Assertion während der Programmentwicklung erkannt werden. (Weitere Informationen zu Assertionen, finden Sie unter [C/C++-Assertionen](/visualstudio/debugger/c-cpp-assertions).)  
  
-   Nicht ordnungsgemäße Ausführung  
  
     Nicht ordnungsgemäße Ausführung umfasst Situationen, in denen Bedingungen außerhalb der Steuerung des Programms, z. B. unzureichenden Arbeitsspeicher oder e/a-Fehler das Ergebnis der Funktion beeinflusst werden. Nicht ordnungsgemäße Situationen sollten durch Abfangen und Auslösen von Ausnahmen behandelt werden.  
  
 Verwenden von Ausnahmen eignet sich besonders für die nicht ordnungsgemäße Ausführung.  
  
##  <a name="_core_mfc_exception_support"></a> Unterstützung für MFC-Ausnahme  
 Ob Sie die C++-Ausnahmen direkt verwenden oder die MFC-Ausnahmemakros, verwenden Sie [CException-Klasse](../mfc/reference/cexception-class.md) oder `CException`-abgeleitete Objekte, die vom Framework oder von der Anwendung ausgelöst werden können.  
  
 Die folgende Tabelle zeigt die vordefinierten Ausnahmen, die von MFC bereitgestellt.  
  
|Ausnahmeklasse|Bedeutung|  
|---------------------|-------------|  
|[CMemoryException-Klasse](../mfc/reference/cmemoryexception-class.md)|Out-of-memory|  
|[CFileException-Klasse](../mfc/reference/cfileexception-class.md)|Datei-Ausnahme|  
|[CArchiveException-Klasse](../mfc/reference/carchiveexception-class.md)|Archivieren/Serialisierung-Ausnahme|  
|[CNotSupportedException-Klasse](../mfc/reference/cnotsupportedexception-class.md)|Als Antwort auf die für nicht unterstützte Dienst anfordern|  
|[CResourceException-Klasse](../mfc/reference/cresourceexception-class.md)|Ausnahme für Windows die ressourcenspeicherbelegung|  
|[CDaoException-Klasse](../mfc/reference/cdaoexception-class.md)|Datenbankausnahmen (DAO-Klassen)|  
|[CDBException-Klasse](../mfc/reference/cdbexception-class.md)|Datenbankausnahmen (ODBC-Klassen)|  
|[COleException-Klasse](../mfc/reference/coleexception-class.md)|OLE-Ausnahmen|  
|[COleDispatchException-Klasse](../mfc/reference/coledispatchexception-class.md)|Ausnahmen Dispatch (Automatisierung)|  
|[CUserException-Klasse](../mfc/reference/cuserexception-class.md)|Ausnahme, die den Benutzer ein Meldungsfeld Warnungen löst dann eine generische [CException-Klasse](../mfc/reference/cexception-class.md)|  
  
> [!NOTE]
>  MFC unterstützt C++-Ausnahmen und die MFC-Ausnahmemakros. MFC bietet keine direkte Unterstützung Windows NT strukturierte Ausnahmehandler (SEH), wie in beschrieben [strukturierte Ausnahmebehandlung](http://msdn.microsoft.com/library/windows/desktop/ms680657).  
  
##  <a name="_core_further_reading_about_exceptions"></a> Weiterführende Themen zu Ausnahmen  
 Die folgenden Artikel wird erläutert, mit der MFC-Bibliothek für die Behandlung der Ausnahme:  
  
-   [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md)  
  
-   [Ausnahmen: Untersuchen von Ausnahmeinhalten](../mfc/exceptions-examining-exception-contents.md)  
  
-   [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md)  
  
-   [Ausnahmen: Ausnahmen in eigenen Funktionen auslösen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)  
  
-   [Ausnahmen: Datenbankausnahmen](../mfc/exceptions-database-exceptions.md)  
  
-   [Ausnahmen: OLE-Ausnahmen](../mfc/exceptions-ole-exceptions.md)  
  
 In den folgenden Artikeln vergleichen die MFC-Ausnahmemakros mit C++-Ausnahmeschlüsselwörter und erläutern, wie Sie Ihren Code anpassen können:  
  
-   [Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)  
  
-   [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md)  
  
-   [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)   
 [Wie erstelle ich meinen eigenen benutzerdefinierten Ausnahmeklassen](http://go.microsoft.com/fwlink/p/?linkid=128045)

