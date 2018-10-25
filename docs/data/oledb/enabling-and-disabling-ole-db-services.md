---
title: Aktivieren und Deaktivieren von OLE DB-Diensten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 72c890b94d84d170bb3ee01bd02d08fc00f9aa04
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50068221"
---
# <a name="enabling-and-disabling-ole-db-services"></a>Aktivieren und Deaktivieren von OLE DB-Diensten

Der OLE DB Service Standortkomponenten-Manager vergleicht die Eigenschaften, die vom Consumer, die vom Anbieter zu bestimmen, ob einzelne Dienstkomponenten aufgerufen werden können, um erweiterte Funktionen, die vom Consumer angeforderte erfüllen unterstützt angegeben werden. Ruft z. B. wenn eine Anwendung, welches einen bildlauffähigen Cursor anfordert, und der Anbieter nur einen Vorwärtscursor unterstützt, die Dienst-Standortkomponenten-Manager die Client-Cursor-Engine-Komponente, um bildlauffähigen Funktionalität bereitzustellen. Wenn die Anwendung setzt voraus, erweiterte Funktionen, die standardmäßig für den Anbieter-Rowset unterstützt dass, und die Anwendung nicht explizit die Eigenschaften, um anzufordern, dass Funktionen, die Funktionalität nicht in dem vom Client zurückgegebenen Rowset scheint festlegt Cursor-Engine. Um interoperable, Anwendungen sollten immer Eigenschaften festlegen, um erweiterte Funktionen explizit anfordern, falls erforderlich.

In einigen Fällen ist es möglicherweise notwendig, einzelne OLE DB-Dienste auch mit vorhandenen Anwendungen arbeiten, die Annahmen zu den Eigenschaften von einem Anbieter zu deaktivieren. OLE DB-Dienste bieten die Möglichkeit, einzelne Dienste oder alle Dienste, die für eine Verbindungs-von-Verbindung oder für alle Anwendungen, die mit einem einzigen Anbieter deaktivieren.

## <a name="see-also"></a>Siehe auch

[OLE DB-Ressourcenpooling und -Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)