---
title: "Unterst&#252;tzen von Transaktionen in OLE&#160;DB | Microsoft Docs"
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
  - "Datenbanken [C++], Transaktionen"
  - "Verteilte Transaktionen [C++]"
  - "Geschachtelte Transaktionen [C++]"
  - "OLE DB [C++], Transaktionsunterstützung"
  - "OLE DB-Consumervorlagen [C++], Transaktionsunterstützung"
  - "Transaktionen [C++], OLE DB-Unterstützung für"
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Unterst&#252;tzen von Transaktionen in OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Eine [Transaktion](../../data/transactions-mfc-data-access.md) ist eine Methode zum Gruppieren \(bzw. Stapeln\) einer Reihe von Aktualisierungen zu einer Datenquelle, sodass entweder alle erfolgreich ausgeführt werden und sofort übermittelt werden oder \(wenn eine von ihnen fehlschlägt\) keine Aktualisierung übergeben und ein Rollback für die ganze Transaktion ausgeführt wird.  Dieser Prozess stellt die Integrität des Ergebnisses hinsichtlich der Datenquelle sicher.  
  
 OLE DB unterstützt Transaktionen mit den folgenden drei Methoden:  
  
-   [\<caps:sentence id\="tgt4" sentenceid\="0699a86bb6d6316bff035b804a56f0aa" class\="tgtSentence"\>ITransactionLocal::StartTransaction\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [\<caps:sentence id\="tgt5" sentenceid\="39299b0fea086b86052550bd165334f7" class\="tgtSentence"\>ITransaction::Commit\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [\<caps:sentence id\="tgt6" sentenceid\="8e992150c28ae247d532408ca7828bfe" class\="tgtSentence"\>ITransaction::Abort\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## Beziehung zwischen Sitzungen und Transaktionen  
 Ein einzelnes Datenquellenobjekt kann ein oder mehrere Sitzungsobjekte erstellen. Jedes dieser Objekte kann sich zu einem bestimmten Zeitpunkt innerhalb oder außerhalb des Gültigkeitsbereichs einer Transaktion befinden.  
  
 Wenn eine Sitzung sich nicht im Bereich einer Transaktion befindet, wirken sich alle im Rahmen dieser Sitzung am Datenspeicher vorgenommenen Arbeiten unmittelbar auf die einzelnen Methodenaufrufe aus. \(Dies wird manchmal als Autocommit\-Modus oder impliziter Modus bezeichnet.\)  
  
 Wenn eine Sitzung in eine Transaktion eintritt, sind alle im Rahmen dieser Sitzung am Datenspeicher vorgenommenen Arbeiten Teil dieser Transaktion und werden als Einheit übermittelt oder abgebrochen. \(Dies wird manchmal als Manualcommit\-Modus bezeichnet.\)  
  
 Die Unterstützung von Transaktionen ist anbieterabhängig.  Wenn der von Ihnen verwendete Anbieter Transaktionen unterstützt, kann ein Sitzungsobjekt, das **ITransaction** und **ITransactionLocal** unterstützt, in den Gültigkeitsbereich einer einfachen \(d. h. nicht geschachtelten\) Transaktion eintreten.  Die OLE DB\-Vorlagenklasse [CSession](../../data/oledb/csession-class.md) unterstützt diese Schnittstellen und wird zur Implementierung der Transaktionsunterstützung in Visual C\+\+ empfohlen.  
  
## Starten und Beenden der Transaktion  
 Sie rufen die Methoden `StartTransaction`, **Commit** und **Abort** im Rowset\-Objekt im Consumer auf.  
  
 Durch das Aufrufen von **ITransactionLocal::StartTransaction** wird eine neue lokale Transaktion gestartet.  Wenn die Transaktion gestartet wurde, wirken sich durch nachfolgende Operationen entstandene Änderungen erst dann auf den Datenspeicher aus, wenn die Transaktion übermittelt wird.  
  
 Durch Aufrufen von **ITransaction::Commit** oder **ITransaction::Abort** wird die Transaktion beendet.  **Commit** bewirkt, dass alle Änderungen im Gültigkeitsbereich der Transaktion auf den Datenspeicher angewendet werden.  **Abort** bewirkt, dass alle Änderungen im Gültigkeitsbereich der Transaktion abgebrochen werden und der Datenspeicher in dem Zustand belassen wird, den er vor dem Start der Transaktion hatte.  
  
## Geschachtelte Transaktionen  
 Eine [geschachtelte Transaktion](https://msdn.microsoft.com/en-us/library/ms716985.aspx) liegt vor, wenn Sie zusätzlich zu einer bereits bestehenden aktiven Transaktion eine neue lokale Transaktion starten.  Die neue Transaktion wird als geschachtelte Transaktion unterhalb der aktuellen Transaktion gestartet.  Wenn der Anbieter keine geschachtelten Transaktionen unterstützt, wird beim Aufrufen von `StartTransaction` bei bereits bestehender aktiver Transaktion im Rahmen dieser Sitzung **XACT\_E\_XTIONEXISTS** zurückgegeben.  
  
## Verteilte Transaktionen  
 Eine verteilte Transaktion aktualisiert verteilte Daten, d. h. Daten, die sich auf mehr als einem vernetzten Computersystem befinden.  Wenn Sie Transaktionen über ein verteiltes System unterstützen möchten, sollten Sie anstelle der OLE DB\-Transaktionsunterstützung .NET Framework verwenden.  
  
## Siehe auch  
 [Verwenden von Accessoren](../../data/oledb/using-accessors.md)