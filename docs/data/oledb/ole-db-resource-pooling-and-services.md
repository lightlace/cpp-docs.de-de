---
title: OLE DB Ressourcenpooling und-Dienste | Microsoft Docs
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
ms.openlocfilehash: ab8c5e5a3e219da7204ef1a1b4942dc70b2f2ad2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ole-db-resource-pooling-and-services"></a>OLE DB-Ressourcenpooling und -Dienste
Um mit OLE DB-pooling oder anderen OLE DB-Diensten arbeiten, muss Ihr Anbieter Aggregation aller Objekte unterstützen. Dies ist eine Voraussetzung für alle OLE DB-1.5 oder höher Anbieter. Es ist wichtig für die Nutzung der Dienste. Anbieter, die Aggregation nicht unterstützen, können nicht in Pools zusammengefasst werden, und keine zusätzliche Dienste bereitgestellt werden.  
  
 Zum Pool hinzugefügt werden soll, müssen der Anbieter das freien Thread-Modell unterstützen. Ressourcenpool bestimmt der Anbieter Threadmodell gemäß der **DBPROP_THREADMODEL** Eigenschaft.  
  
 Wenn der Anbieter einen globalen Verbindungszustand, die sich ändern kann verfügt, während sich die Datenquelle im initialisierten Zustand befindet, sollte die neue unterstützen **DBPROP_RESETDATASOURCE** Eigenschaft. Diese Eigenschaft wird aufgerufen, bevor eine Verbindung wird wiederverwendet, und dem Anbieter die Möglichkeit gibt, um den Zustand vor der nächsten Verwendung zu bereinigen. Wenn ein Zustand, der der Verbindung zugeordnete der Anbieter nicht bereinigt werden kann, kann er zurück **DBPROPSTATUS_NOTSETTABLE** für die Eigenschaft und die Verbindung nicht wiederverwendet werden.  
  
 Anbieter, die eine Verbindung mit einer Remotedatenbank herstellen und können erkennen, ob die Verbindung möglicherweise verlorengegangenen unterstützen sollte die **DBPROP_CONNECTIONSTATUS** Eigenschaft. Diese Eigenschaft bietet der OLE DB-Dienste die Möglichkeit, inaktive Verbindungen zu erkennen, und stellen Sie sicher, dass sie nicht an den Pool zurückgegeben werden.  
  
 Schließlich werden automatische Eintragung von Transaktionen ist grundsätzlich nicht möglich, es sei denn, es auf der gleichen Ebene implementiert wird, das pooling. Anbieter, die automatische Eintragung von Transaktionen selbst unterstützen sollte unterstützen deaktivieren diese Eintragung, verfügbar machen, die **DBPROP_INIT_OLEDBSERVICES** -Eigenschaft und die Eintragung deaktivieren, wenn die **DBPROPVAL_OS_ TXNENLISTMENT** ist standardmäßig deaktiviert.  
  
## <a name="see-also"></a>Siehe auch  
 [Erweiterte Anbietertechniken](../../data/oledb/advanced-provider-techniques.md)