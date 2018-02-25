---
title: "Unterstützen von Transaktionen in OLE DB | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 84849b2d9bfd899a0ffd8a5d8eafe12f91a4adce
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="supporting-transactions-in-ole-db"></a>Unterstützen von Transaktionen in OLE DB
Ein [Transaktion](../../data/transactions-mfc-data-access.md) lässt sich eine Gruppe oder ein batch, eine Reihe von Updates mit einer Datenquelle so, dass entweder alle erfolgreich ausgeführt werden und gleichzeitig ein Commit ausgeführt werden, oder (Wenn eine von Ihnen ein Fehler auftritt) sind keine ein Commit ausgeführt wurde und die gesamte Transaktion zurückgesetzt wird. Dieser Prozess wird sichergestellt, dass die Integrität des Ergebnisses in der Datenquelle.  
  
 OLE DB unterstützt Transaktionen mit den folgenden drei Methoden:  
  
-   [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/en-us/library/ms709786.aspx)  
  
-   [ITransaction::Commit](https://msdn.microsoft.com/en-us/library/ms713008.aspx)  
  
-   [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx)  
  
## <a name="relationship-of-sessions-and-transactions"></a>Beziehung zwischen Sitzungen und Transaktionen  
 Ein einzelnes Datenquellenobjekt kann eine oder mehrere Sitzungsobjekte erstellen, von die jeder innerhalb oder außerhalb des Bereichs einer Transaktion zu einem bestimmten Zeitpunkt sein kann.  
  
 Wenn eine Sitzung eine Transaktion nicht eingeben, wird wird bei jedem Methodenaufruf sofort alle Arbeit, die in dieser Sitzung auf den Datenspeicher ein Commit ausgeführt. (Dies wird manchmal als Autocommit-Modus oder impliziter Modus bezeichnet.)  
  
 Gelangt eine Sitzung eine Transaktion, wird alle Arbeit, die in dieser Sitzung auf den Datenspeicher ist Teil der Transaktion und ein Commit oder Abbruch als Einheit. (Dies wird manchmal als Manualcommit-Modus bezeichnet.)  
  
 Unterstützung von Transaktionen ist anbieterspezifisch. Wenn der Anbieter, die Sie verwenden Transaktionen, die ein Sitzungsobjekt unterstützt, die unterstützt **ITransaction** und **ITransactionLocal** können eine einfache eingeben (d. h. nicht geschachtelten) Transaktion. Die Klasse des OLE DB-Vorlagen [CSession](../../data/oledb/csession-class.md) unterstützt diese Schnittstellen und ist die empfohlene Vorgehensweise für die Unterstützung von Transaktionen in Visual C++ implementiert.  
  
## <a name="starting-and-ending-the-transaction"></a>Starten und Beenden der Transaktion  
 Rufen Sie die `StartTransaction`, **Commit**, und **Abort** Methoden im Rowsetobjekt im Consumer.  
  
 Aufrufen von **ITransactionLocal:: StartTransaction** startet eine neue lokale Transaktion. Beim Starten der Transaktions werden alle Änderungen, die von nachfolgenden Vorgänge werden nicht tatsächlich im Datenspeicher angewendet der Transaktion endgültig.  
  
 Aufrufen von **ITransaction:: Commit** oder **ITransaction:: Abort** beendet die Transaktion. **Commit** bewirkt, dass alle Änderungen innerhalb des Bereichs der Transaktion auf den Datenspeicher angewendet werden soll. **Abort** Ursachen, die alle Änderungen innerhalb des Bereichs der Transaktion abgebrochen wird, und der Datenspeicher ist verbleibt im Status er hatte, vor dem Start der Transaktion.  
  
## <a name="nested-transactions"></a>Geschachtelte Transaktionen  
 Ein [geschachtelten Transaktionen](https://msdn.microsoft.com/en-us/library/ms716985.aspx) tritt auf, wenn Sie eine neue lokale Transaktion starten, wenn die Sitzung bereits eine aktive Transaktion vorhanden ist. Die neue Transaktion wird als geschachtelte Transaktion unter der aktuellen Transaktion gestartet. Wenn der Anbieter keine geschachtelten Transaktionen unterstützt, beim Aufrufen von `StartTransaction` die Sitzung gibt zurück, wenn bereits eine aktive Transaktion auf **XACT_E_XTIONEXISTS**.  
  
## <a name="distributed-transactions"></a>Verteilte Transaktionen  
 Eine verteilte Transaktion ist eine Transaktion, die verteilte Daten aktualisiert. d. h. die Daten auf mehreren vernetzten Computersystemen. Wenn Sie Transaktionen über ein verteiltes System unterstützen möchten, sollten Sie .NET Framework anstelle der OLE DB-transaktionsunterstützung verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Zugriffsmethoden](../../data/oledb/using-accessors.md)