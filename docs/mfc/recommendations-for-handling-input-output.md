---
title: "Empfehlungen für das Behandeln von e / a | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- I/O [MFC], about I/O
- file-based I/O options
- I/O [MFC]
- I/O [MFC], options
- I/O [MFC], file-based options
ms.assetid: d664b175-3b4a-40c3-b14b-39de6b12e419
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc7fbb58aa1ac85c185756eb336737cbaf33a48e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recommendations-for-handling-inputoutput"></a>Empfehlungen zur Eingabe-/Ausgabebehandlung
Gibt an, ob Sie dateibasierte e/a nicht verwenden, hängt davon ab, wie Sie die Fragen in der folgenden Entscheidungsstruktur beantworten:  
  
 **Der primären Daten in der Anwendung in einer Datenträgerdatei befinden**  
  
-   Ja, befindet sich die primären Daten in eine Datei ein:  
  
     **Die Anwendung die gesamte Datei zu lesen, in den Arbeitsspeicher auf die Datei öffnen und die gesamte Datei wieder auf dem Datenträger festgeschrieben auf die Datei zu speichern**  
  
    -   Ja: Dies gilt standardmäßig MFC-Dokument. Verwendung **CDocument** Serialisierung.  
  
    -   No: Dies ist normalerweise die Groß-/Kleinschreibung transaktionsbasierten Aktualisieren der Datei. Aktualisieren Sie die Datei auf der Basis eines pro Transaktion und müssen nicht **CDocument** Serialisierung.  
  
-   Nein, nicht die primären Daten in einer Datenträgerdatei befinden:  
  
     **Die Daten in einer ODBC-Datenquelle gespeichert werden**  
  
    -   Ja, befindet sich die Daten in einer ODBC-Datenquelle ein:  
  
         Verwenden MFCs-datenbankunterstützung. Die standard-MFC-Implementierung für diesen Fall enthält eine `CDatabase` -Objekts, wie im Artikel erläutert [MFC: Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md). Die Anwendung möglicherweise auch lesen und schreiben eine zusätzliche Datei – des Zweckes der Anwendungs-Assistent "unterstützen eine Datenbanksicht und die Datei"-Option. In diesem Fall verwenden Sie die Serialisierung für die zusätzliche Datei.  
  
    -   Nein, nicht die Daten in einer ODBC-Datenquelle befinden.  
  
         Beispiele für diesen Fall: die Daten befindet sich in einem nicht - ODBC DBMS; die Daten werden über einen anderen Mechanismus, wie z. B. OLE oder DDE gelesen.  
  
         In solchen Fällen Serialisierung nicht verwenden, und Ihre Anwendung keine geöffneten und Menüelemente zu speichern. Sie können weiterhin verwenden möchten eine **CDocument** als Basis Home, ebenso wie eine MFC-ODBC Anwendung wird das Dokument verwendet zum Speichern von `CRecordset` Objekte. Aber Sie können das Framework Standardserialisierung Datei öffnen oder speichern Dokument nicht verwendet.  
  
 Zur Unterstützung von öffnen, speichern, und speichern Sie als Befehle im Menü Datei, bietet das Framework Dokumentserialisierung. Die Serialisierung liest und schreibt Daten, z. B. Objekte, die von Klasse abgeleitet `CObject`, zu dauerhaften Speicher, normalerweise eine Datenträgerdatei. Serialisierung ist einfach zu verwenden und viele der Ihre Anforderungen erfüllt, aber möglicherweise im viele formularbasierten datenzugriffsanwendungen nicht zulässig. Formularbasierten datenzugriffsanwendungen Aktualisierungsdaten in der Regel auf Basis eines pro Transaktion. Sie zum Aktualisieren der Datensätze, die von der Transaktion statt lesen und schreiben eine gesamte Datei auf einmal betroffen sind.  
  
 Weitere Informationen zur Serialisierung finden Sie unter [Serialisierung](../mfc/serialization-in-mfc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung: Serialisierung im Vergleich zur Datenbank-e/a](../mfc/serialization-serialization-vs-database-input-output.md)
