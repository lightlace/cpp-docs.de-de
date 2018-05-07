---
title: Aktivieren und Deaktivieren von OLE DB-Dienste | Microsoft Docs
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
ms.openlocfilehash: 785997cafec76bfa438382ace6930d53c31c4dc9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="enabling-and-disabling-ole-db-services"></a>Aktivieren und Deaktivieren von OLE DB-Diensten
Komponenten-Manager für OLE DB-Dienst vergleicht die Eigenschaften, die vom Consumer vom Anbieter, um festzustellen, ob einzelne Dienstkomponenten aufgerufen werden können, um erweiterte Funktionalität, die vom Consumer angeforderte erfüllen unterstützten angegeben werden. Wenn eine Anwendung, welches einen bildlauffähigen Cursor anfordert, und der Anbieter nur einen Vorwärtscursor unterstützt, ruft die Dienst-Standortkomponenten-Manager die Client-Cursormoduls-Dienstkomponente um bildlauffähigen Funktionalität bereitzustellen. Wenn die Anwendung ist auf die erweiterten Funktionen, die standardmäßig für den Anbieter-Rowset unterstützt zurückzugreifen, und die Anwendung nicht explizit die Eigenschaften, um anzufordern, dass Funktionen, die Funktionalität für das vom Client zurückgegebenen Rowset nicht angezeigt wird ggf. Cursor-Modul. Um interoperable werden Anwendungen sollten immer Eigenschaften festlegen, um erweiterte Funktionalität explizit anfordern, falls erforderlich.  
  
 In einigen Fällen ist es möglicherweise notwendig, einzelne OLE DB-Dienste mit vorhandenen Anwendungen optimiert, die Annahmen über die Merkmale eines Anbieters treffen zu deaktivieren. OLE DB-Dienste bieten die Möglichkeit, einzelne Dienste oder alle Dienste, entweder für eine Verbindung von Verbindung oder für alle Anwendungen, die über einen einzelnen Anbieter deaktivieren.  
  
## <a name="see-also"></a>Siehe auch  
 [OLE DB-Ressourcenpooling und -Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)