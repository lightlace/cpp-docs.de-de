---
title: OLE DB-Ressourcenpooling und -Dienste
ms.date: 10/29/2018
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
ms.openlocfilehash: f46c6f493ae41570c75c384fcc836707faeab99f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023749"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB-Ressourcenpooling und -Dienste

Um mit OLE DB-pooling oder bei jedem anderen OLE DB-Dienst funktioniert, muss Ihr Anbieter Aggregation aller Objekte unterstützen. Dies ist eine Voraussetzung für alle OLE DB-1.5 oder höher Anbieter. Es ist wichtig für die Nutzung von Diensten. Anbieter, die Aggregation nicht unterstützen können nicht in Pools zusammengefasst werden, und keine zusätzliche Dienste bereitgestellt werden.

Zum Pool hinzugefügt werden soll, müssen der Anbieter des freien Thread-Modells unterstützen. Der Ressourcenpool bestimmt das Modell des Anbieters Thread gemäß der DBPROP_THREADMODEL-Eigenschaft.

Wenn der Anbieter einen globalen Verbindungszustand, der sich ändern kann verfügt, während sich die Datenquelle im initialisierten Zustand befindet, sollte er die neue DBPROP_RESETDATASOURCE-Eigenschaft unterstützen. Diese Eigenschaft wird aufgerufen, bevor eine Verbindung erneut verwendet wird und gibt dem Anbieter die Möglichkeit, um den Zustand vor der nächsten Verwendung zu bereinigen. Wenn der Anbieter sich einem Zustand der Verbindung zugeordnete bereinigen kann, kann es DBPROPSTATUS_NOTSETTABLE zurückgegeben, für die Eigenschaft, und die Verbindung wird nicht wiederverwendet werden.

Anbieter, die mit einer Remotedatenbank verbunden und können erkennen, ob die Verbindung verloren gehen kann, sollte die DBPROP_CONNECTIONSTATUS-Eigenschaft unterstützen. Diese Eigenschaft gibt die OLE DB-Dienste die Möglichkeit, inaktive Verbindungen zu erkennen, und stellen Sie sicher, dass sie sich an den Pool zurückgegeben werden nicht.

Zum Schluss funktioniert automatische Eintragung von Transaktionen in der Regel nicht, wenn sie auf der gleichen Ebene implementiert ist, das pooling. Anbieter, die automatische Eintragung von Transaktionen unterstützen sollten unterstützen deaktivieren diese Eintragung durch die DBPROP_INIT_OLEDBSERVICES-Eigenschaft und die Eintragung deaktivieren, wenn DBPROPVAL_OS_TXNENLISTMENT deaktiviert wird.

## <a name="see-also"></a>Siehe auch

[Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)