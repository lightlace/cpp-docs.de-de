---
title: Empfehlungen für die Behandlung von e / a | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a8d0d2c7e560338bbef5cbe432c325385734c56
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385026"
---
# <a name="recommendations-for-handling-inputoutput"></a>Empfehlungen zur Eingabe-/Ausgabebehandlung

Gibt an, ob Sie dateibasierte e/a verwenden, hängt davon ab, wie Sie auf die Fragen in der folgenden Entscheidungsstruktur reagieren:

**Die primären Daten in Ihrer Anwendung in der Datei auf einem Datenträger gespeichert werden**

- Ja, können Sie die primären Daten in einer Datenträgerdatei gespeichert:

     **Die Anwendung die gesamte Datei gelesen, in den Arbeitsspeicher auf die Datei öffnen und Zurückschreiben die gesamte Datei auf dem Datenträger auf die Datei zu speichern**

   - Ja: Dies ist der standardmäßigen MFC-Dokument Fall. Verwendung `CDocument` Serialisierung.

   - Nein: Dies ist in der Regel die Groß-/Kleinschreibung transaktionsbasierten Aktualisieren der Datei. Sie aktualisieren Sie die Datei auf einer Basis pro Transaktion und keine `CDocument` Serialisierung.

- Nein, nicht die primären Daten in eine Datenträgerdatei befinden:

     **Die Daten in einer ODBC-Datenquelle gespeichert werden**

   - Ja, befindet sich die Daten in einer ODBC-Datenquelle ein:

         Use MFC's database support. The standard MFC implementation for this case includes a `CDatabase` object, as discussed in the article [MFC: Using Database Classes with Documents and Views](../data/mfc-using-database-classes-with-documents-and-views.md). The application might also read and write an auxiliary file — the purpose of the application wizard "both a database view and file support" option. In this case, you'd use serialization for the auxiliary file.

   - Nein, nicht die Daten in einer ODBC-Datenquelle befinden.

         Examples of this case: the data resides in a non-ODBC DBMS; the data is read via some other mechanism, such as OLE or DDE.

         In such cases, you won't use serialization, and your application won't have Open and Save menu items. You might still want to use a `CDocument` as a home base, just as an MFC ODBC application uses the document to store `CRecordset` objects. But you won't use the framework's default File Open/Save document serialization.

Zur Unterstützung von öffnen, speichern, und wie die Befehle im Menü Datei speichern, stellt das Framework Dokumentserialisierung bereit. Serialisierung liest und schreibt Daten, z. B. Objekte aus der Klasse abgeleitete `CObject`, zu dauerhaften Speicher, normalerweise eine Datenträgerdatei. Serialisierung ist einfach zu verwenden, und viele der Ihre Anforderungen erfüllt, aber es kann in vielen Datenzugriffs-Anwendungen nicht geeignet sein. Formularbasierten datenzugriffsanwendungen aktualisieren in der Regel Daten für die pro Transaktion. Sie aktualisieren die Datensätze, die von der Transaktion statt das Lesen und schreiben eine ganze Datei gleichzeitig betroffen sind.

Weitere Informationen zur Serialisierung finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).

## <a name="see-also"></a>Siehe auch

[Serialisierung: Serialisierung im Vergleich zur Datenbankeingabe/-Ausgabe](../mfc/serialization-serialization-vs-database-input-output.md)
