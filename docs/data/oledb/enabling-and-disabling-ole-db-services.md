---
title: Aktivieren und Deaktivieren von OLE DB-Diensten
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: df17a55950b03d4d63dea2199e3bc19bedb8a7e3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028953"
---
# <a name="enabling-and-disabling-ole-db-services"></a>Aktivieren und Deaktivieren von OLE DB-Diensten

Der OLE DB Service Standortkomponenten-Manager vergleicht die Eigenschaften, die vom Consumer an den Eigenschaften, die vom Anbieter zu bestimmen, ob einzelne Dienstkomponenten verwendet werden können, um erweiterte Funktionen, die vom Consumer angeforderte erfüllen unterstützt angegeben werden. Verwendet beispielsweise wenn eine Anwendung, welches einen bildlauffähigen Cursor anfordert, und der Anbieter nur einen Vorwärtscursor unterstützt, die Dienst-Standortkomponenten-Manager die Client-Cursor-Engine-Komponente bildlauffähigen Funktionalität bereitstellen. Wenn die Anwendung setzt voraus, erweiterte Funktionen, die standardmäßig für den Anbieter-Rowset unterstützt dass, und die Anwendung nicht explizit legen Sie die Eigenschaften, um anzufordern, dass Funktionen, die Funktionalität nicht in dem vom Client zurückgegebenen Rowset angezeigt werden kann Cursor-Engine. Um interoperable, Anwendungen sollten immer Eigenschaften festlegen, um erweiterte Funktionen explizit anfordern, falls erforderlich.

In einigen Fällen ist es möglicherweise notwendig, einzelne OLE DB-Dienste auch mit vorhandenen Anwendungen arbeiten, die Annahmen zu den Eigenschaften von einem Anbieter zu deaktivieren. OLE DB-Dienste bieten die Möglichkeit, einzelne Dienste oder alle Dienste, die für eine Verbindungs-von-Verbindung oder für alle Anwendungen, die mit einem einzigen Anbieter deaktivieren.

## <a name="see-also"></a>Siehe auch

[OLE DB-Ressourcenpooling und -Dienste](../../data/oledb/ole-db-resource-pooling-and-services.md)