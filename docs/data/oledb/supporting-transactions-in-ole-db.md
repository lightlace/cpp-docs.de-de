---
title: Unterstützen von Transaktionen in OLE DB | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumer templates [C++], transaction support
- transactions [C++], OLE DB support for
- nested transactions [C++]
- OLE DB [C++], transaction support
- databases [C++], transactions
- distributed transactions [C++]
ms.assetid: 3d72e583-ad38-42ff-8f11-e2166d60a5a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 47b869ffc6ad3dd1492ab052d648bcb8acde7e52
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49083696"
---
# <a name="supporting-transactions-in-ole-db"></a>Unterstützen von Transaktionen in OLE DB

Ein [Transaktion](../../data/transactions-mfc-data-access.md) ist eine Möglichkeit, eine Gruppe oder einem Batch zusammenfassen, eine Reihe von Updates mit einer Datenquelle, damit entweder alle erfolgreich ausgeführt werden und gleichzeitig ein Commit ausgeführt werden, oder (Wenn eine der davon ausfällt) sind keine ein Commit ausgeführt, und die gesamte Transaktion zurückgesetzt wird. Dadurch wird sichergestellt, die Integrität des Ergebnisses, auf die Datenquelle.  
  
OLE DB unterstützt Transaktionen mit den folgenden drei Methoden:  
  
- [ITransactionLocal::StartTransaction](/previous-versions/windows/desktop/ms709786)  
  
- [ITransaction::Commit](/previous-versions/windows/desktop/ms713008)  
  
- [ITransaction::Abort](/previous-versions/windows/desktop/ms709833)  
  
## <a name="relationship-of-sessions-and-transactions"></a>Beziehung zwischen Sitzungen und Transaktionen  

Ein einzelnes Objekt kann eine oder mehrere Sitzungsobjekte erstellen, von die jeder innerhalb oder außerhalb des Bereichs einer Transaktion zu einem bestimmten Zeitpunkt sein kann.  
  
Wenn eine Sitzung eine Transaktion nicht eingeben, wird wird bei jedem Methodenaufruf sofort alle Arbeit, die innerhalb dieser Sitzung für den Datenspeicher ein Commit ausgeführt. (Dies wird manchmal als Autocommit-Modus oder impliziter Modus bezeichnet.)  
  
Wenn eine Sitzung eine Transaktion eingibt, alle Aufgaben innerhalb dieser Sitzung ausgeführt wird, für den Datenspeicher ist Teil der Transaktion und ein Commit ausgeführt oder wurde abgebrochen, als einzelne Einheit. (Dies wird manchmal als Manualcommit-Modus bezeichnet.)  
  
Unterstützung von Transaktionen ist anbieterspezifisch. Wenn der Anbieter, die Sie verwenden Transaktionen, die ein Sitzungsobjekt unterstützt, die unterstützt `ITransaction` und `ITransactionLocal` können ein einfaches eingeben (d. h. nicht geschachtelten) Transaktion. Die Klasse des OLE DB-Vorlagen [CSession](../../data/oledb/csession-class.md) unterstützt diese Schnittstellen und die empfohlene Vorgehensweise für das transaktionsunterstützung in Visual C++ implementiert wird.  
  
## <a name="starting-and-ending-the-transaction"></a>Starten und Beenden der Transaktion  

Rufen Sie die `StartTransaction`, `Commit`, und `Abort` Methoden in das Rowsetobjekt, das im Consumer.  
  
Aufrufen von `ITransactionLocal::StartTransaction` startet eine neue lokale Transaktion. Wenn Sie die Transaktion starten, alle Änderungen, die durch nachfolgende Vorgänge beauftragt tatsächlich mit dem Datenspeicher gelten nicht, bis Sie die Transaktion ein commit.  
  
Aufrufen von `ITransaction::Commit` oder `ITransaction::Abort` beendet die Transaktion. `Commit` bewirkt, dass alle Änderungen innerhalb des Bereichs der Transaktion, die mit dem Datenspeicher angewendet werden. `Abort` bewirkt, dass alle Änderungen innerhalb des Bereichs der Transaktion abgebrochen werden soll und dem Datenspeicher wird im Status belassen, es vor der die Transaktion gestartet wurde.  
  
## <a name="nested-transactions"></a>Geschachtelte Transaktionen  

Ein [geschachtelten Transaktionen](/previous-versions/windows/desktop/ms716985) tritt auf, wenn Sie eine neue lokale Transaktion starten, wenn die Sitzung bereits eine aktive Transaktion vorhanden ist. Die neue Transaktion wird als eine geschachtelte Transaktion unter der aktuellen Transaktion gestartet. Wenn der Anbieter geschachtelte Transaktionen nicht unterstützt, wird beim Aufrufen `StartTransaction` bei bereits gibt eine aktive Transaktion in der Sitzung wird XACT_E_XTIONEXISTS zurückgegeben.  
  
## <a name="distributed-transactions"></a>Verteilte Transaktionen  

Eine verteilte Transaktion ist eine Transaktion, die verteilte Daten aktualisiert. d. h. die Daten auf mehreren vernetzten Computersystemen befinden. Wenn Sie Transaktionen über ein verteiltes System unterstützen möchten, sollten Sie .NET Framework anstelle der OLE DB-transaktionsunterstützung verwenden.  
  
## <a name="see-also"></a>Siehe auch  

[Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)