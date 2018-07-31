---
title: OLE DB-Ressourcenpooling und-Dienste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- resource pooling [OLE DB], provider requirements
- OLE DB, resource pooling
- service providers [OLE DB]
- OLE DB services [OLE DB], provider requirements
- OLE DB services [OLE DB]
- OLE DB providers, resource pooling
ms.assetid: 360c36e2-25ae-4caf-8ee7-d4a6b6898f68
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c2a04d0b990906f9f124edc9dbda71d65127e4ed
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338560"
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB-Ressourcenpooling und -Dienste
Um mit OLE DB-pooling oder bei jedem anderen OLE DB-Dienst funktioniert, muss Ihr Anbieter Aggregation aller Objekte unterstützen. Dies ist eine Voraussetzung für alle OLE DB-1.5 oder höher Anbieter. Es ist wichtig für die Nutzung von Diensten. Anbieter, die keine Aggregation unterstützen, können nicht in einem Pool werden und keine zusätzliche Dienste bereitgestellt werden.  
  
 Zum Pool hinzugefügt werden soll, müssen der Anbieter des freien Thread-Modells unterstützen. Ressourcenpool bestimmt das Modell des Anbieters Thread gemäß der `DBPROP_THREADMODEL` Eigenschaft.  
  
 Wenn der Anbieter einen globalen Verbindungszustand, die sich ändern kann verfügt, während sich die Datenquelle im initialisierten Zustand befindet, sollte das neue unterstützen `DBPROP_RESETDATASOURCE` Eigenschaft. Diese Eigenschaft wird aufgerufen, bevor eine Verbindung erneut verwendet wird und gibt dem Anbieter die Möglichkeit, um den Zustand vor der nächsten Verwendung zu bereinigen. Wenn der Anbieter sich einem Zustand der Verbindung zugeordnete bereinigen kann, kann es zurückgeben `DBPROPSTATUS_NOTSETTABLE` für die Eigenschaft und die Verbindung nicht wiederverwendet werden.  
  
 Anbieter, die mit einer Remotedatenbank verbunden und können erkennen, ob es sich bei, dass die Verbindung verloren gehen kann unterstützen soll die `DBPROP_CONNECTIONSTATUS` Eigenschaft. Diese Eigenschaft gibt die OLE DB-Dienste die Möglichkeit, inaktive Verbindungen zu erkennen, und stellen Sie sicher, dass sie nicht an den Pool zurückgegeben werden.  
  
 Schließlich funktioniert die automatische transaktionseintragung in der Regel nicht, es sei denn, es auf der gleichen Ebene implementiert wird, das pooling. Anbieter, die automatische Eintragung von Transaktionen selbst unterstützen sollten deaktivieren diese Eintragung durch Verfügbarmachen von unterstützen die `DBPROP_INIT_OLEDBSERVICES` -Eigenschaft und die Eintragung zu deaktivieren, wenn die `DBPROPVAL_OS_TXNENLISTMENT` deaktiviert ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)