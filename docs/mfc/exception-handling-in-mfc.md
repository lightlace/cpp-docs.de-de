---
title: Ausnahmebehandlung in MFC
ms.date: 11/04/2016
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
ms.openlocfilehash: afa49a4d54397cf79a3bd0af28e4a0f0a4c7639e
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818634"
---
# <a name="exception-handling-in-mfc"></a>Ausnahmebehandlung in MFC

Dieser Artikel erläutert die Ausnahmebehandlungsmechanismen in MFC verfügbare. Es stehen zwei Mechanismen zur Verfügung:

- C++-Ausnahmen, die in MFC-Version 3.0 und höher verfügbar

- Die MFC-Ausnahmemakros in MFC-Versionen 1.0 und höher verfügbar

Wenn Sie eine neue Anwendung unter Verwendung von MFC schreiben, sollten Sie den C++-Mechanismus verwenden. Sie können die Makro-basierten Mechanismus verwenden, wenn Ihre vorhandene Anwendung bereits diesen Mechanismus ausgiebig verwendet.

Sie können leicht vorhandenen Code anpassen und Verwenden von C++-Ausnahmen statt der MFC-Ausnahmemakros konvertieren. Vorteile der Konvertierung von Code und Richtlinien für die auf diese Weise werden in diesem Artikel beschrieben [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md).

Wenn Sie bereits eine Anwendung mit der MFC-Ausnahmemakros entwickelt haben, können Sie weiterhin verwenden dieser Makros im vorhandenen Code, bei der Verwendung von C++-Ausnahmen im neuen Code. Der Artikel [Ausnahmen: Änderungen an Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md) stellt Richtlinien für die auf diese Weise.

> [!NOTE]
>  Um C++-Ausnahmebehandlung in Ihrem Code zu aktivieren, wählen Sie auf den C++-Ausnahmen aktivieren, auf der Seite der Generierung von Code im C/C++-Ordner des Projekts [Eigenschaftenseiten](../build/reference/property-pages-visual-cpp.md) (Dialogfeld), oder verwenden Sie die [/EHsc](../build/reference/eh-exception-handling-model.md) -Compileroption.

In diesem Artikel werden die folgenden Themen behandelt:

- [Bei Verwendung von Ausnahmen](#_core_when_to_use_exceptions)

- [Unterstützung von MFC-Ausnahmen](#_core_mfc_exception_support)

- [Weitere Informationen über Ausnahmen](#_core_further_reading_about_exceptions)

##  <a name="_core_when_to_use_exceptions"></a> Bei Verwendung von Ausnahmen

Drei Kategorien von Ergebnissen können auftreten, wenn eine Funktion, die während der programmausführung aufgerufen wird: normale Ausführung oder fehlerhafte Ausführung nicht normale Ausführung. Jede Kategorie wird unten beschrieben.

- Normale Ausführung

   Die Funktion kann normalerweise ausgeführt und zurückgegeben. Einige Funktionen geben einen Ergebniscode zurück, an den Aufrufer, der das Ergebnis der Funktion angibt. Die möglichen Ergebniscodes sind ausschließlich für die Funktion definiert und den Bereich von möglichen Ergebnissen der Funktion darstellen. Der resultierende Code kann darauf hinweisen, Erfolg oder Fehler oder eine bestimmte Art von Fehler, die innerhalb des normalen Bereichs von Erwartungen kann auch angeben. Beispielsweise kann eine Datei-Status-Funktion einen Code zurückgeben, der angibt, dass die Datei nicht vorhanden ist. Beachten Sie, dass der Begriff 'Fehlercode' nicht verwendet wird, da ein Ergebniscode eines von vielen erwarteten Ergebnissen darstellt.

- Fehlerhafte Ausführung

   Der Aufrufer einige Fehler bei der Übergabe von Argumenten an die Funktion macht, oder ruft die Funktion in einem ungeeigneten Kontext. Diese Situation tritt ein Fehler, und es sollte eine Assertion während der Programmentwicklung erkannt werden. (Weitere Informationen zu Assertionen, finden Sie unter [C/C++-Assertionen](/visualstudio/debugger/c-cpp-assertions).)

- Nicht normale Ausführung

   Nicht normale Ausführung umfasst Situationen, in denen Bedingungen außerhalb der Steuerung des Programms, wie z. B. nicht genügend Arbeitsspeicher oder e/a-Fehler das Ergebnis der Funktion beeinflussen, sind. Ungewöhnliche Situationen sollten durch Abfangen und Auslösen von Ausnahmen behandelt werden.

Verwenden von Ausnahmen ist besonders geeignet für die nicht ordnungsgemäße Ausführung.

##  <a name="_core_mfc_exception_support"></a> Unterstützung von MFC-Ausnahmen

Ob Sie die C++-Ausnahmen direkt verwenden oder verwenden Sie die MFC-Ausnahmemakros, verwenden Sie [CException-Klasse](../mfc/reference/cexception-class.md) oder `CException`-abgeleiteten Objekte aus, die vom Framework oder von der Anwendung ausgelöst werden können.

Die folgende Tabelle zeigt die vordefinierten Ausnahmen, die von MFC bereitgestellten.

|Ausnahmeklasse|Bedeutung|
|---------------------|-------------|
|[CMemoryException-Klasse](../mfc/reference/cmemoryexception-class.md)|Out-of-memory|
|[CFileException-Klasse](../mfc/reference/cfileexception-class.md)|Datei-Ausnahme|
|[CArchiveException-Klasse](../mfc/reference/carchiveexception-class.md)|Archivieren und Serialisierung-Ausnahme|
|[CNotSupportedException-Klasse](../mfc/reference/cnotsupportedexception-class.md)|Als Antwort auf die für nicht unterstützte Dienst anfordern|
|[CResourceException-Klasse](../mfc/reference/cresourceexception-class.md)|Ausnahme für Windows die ressourcenspeicherbelegung|
|[CDaoException-Klasse](../mfc/reference/cdaoexception-class.md)|Datenbankausnahmen (DAO-Klassen)|
|[CDBException-Klasse](../mfc/reference/cdbexception-class.md)|Datenbankausnahmen (ODBC-Klassen)|
|[COleException-Klasse](../mfc/reference/coleexception-class.md)|OLE-Ausnahmen|
|[COleDispatchException-Klasse](../mfc/reference/coledispatchexception-class.md)|Ausnahmen für die Verteilung (Automatisierung)|
|[CUserException-Klasse](../mfc/reference/cuserexception-class.md)|Ausnahme, die den Benutzer ein Meldungsfeld Warnungen löst dann eine generische [CException-Klasse](../mfc/reference/cexception-class.md)|

> [!NOTE]
>  MFC unterstützt sowohl die MFC-Ausnahmemakros als auch C++-Ausnahmen. MFC bietet keine direkte Unterstützung Windows NT, strukturierte Ausnahmehandler (SEH), siehe [Structured Exception Handling](/windows/desktop/debug/structured-exception-handling).

##  <a name="_core_further_reading_about_exceptions"></a> Weitere Informationen über Ausnahmen

In den folgenden Artikeln wird erläutert, mit der MFC-Bibliothek für die Behandlung der Ausnahme:

- [Ausnahmen: Abfangen und Löschen von Ausnahmen](../mfc/exceptions-catching-and-deleting-exceptions.md)

- [Ausnahmen: Untersuchen von Ausnahmeinhalten](../mfc/exceptions-examining-exception-contents.md)

- [Ausnahmen: Freigeben von Objekten in Ausnahmen](../mfc/exceptions-freeing-objects-in-exceptions.md)

- [Ausnahmen: Auslösen von Ausnahmen in eigenen Funktionen](../mfc/exceptions-throwing-exceptions-from-your-own-functions.md)

- [Ausnahmen: Datenbankausnahmen](../mfc/exceptions-database-exceptions.md)

- [Ausnahmen: OLE-Ausnahmen](../mfc/exceptions-ole-exceptions.md)

In den folgenden Artikeln vergleichen die MFC-Ausnahmemakros, mit der C++-Ausnahmeschlüsselwörter und erläutern, wie Sie Ihren Code anpassen können:

- [Ausnahmen: Änderungen für Ausnahmemakros in Version 3.0](../mfc/exceptions-changes-to-exception-macros-in-version-3-0.md)

- [Ausnahmen: Umwandeln von MFC-Ausnahmemakros](../mfc/exceptions-converting-from-mfc-exception-macros.md)

- [Ausnahmen: Verwenden von MFC-Makros und C++-Ausnahmen](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md)

## <a name="see-also"></a>Siehe auch

[C++-Ausnahmebehandlung](../cpp/cpp-exception-handling.md)<br/>
[Gewusst wie: Erstellen Sie eigene benutzerdefinierte Ausnahmeklassen](http://go.microsoft.com/fwlink/p/?linkid=128045)
