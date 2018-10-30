---
title: Eigenschaftenzuordnungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/24/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2c6c3ddc4b19cd9b65203d8a5e675b9ed75720a1
ms.sourcegitcommit: 840033ddcfab51543072604ccd5656fc6d4a5d3a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/29/2018
ms.locfileid: "50216460"
---
# <a name="property-maps"></a>Eigenschaftenzuordnungen

Die Sitzung, Rowset und optional Command-Objekt unterstützt jeder Anbieter eine oder mehrere Eigenschaften. Diese Eigenschaften werden in der eigenschaftenzuordnungen, die in den Headerdateien, die von erstellten gespeicherten definiert die **OLE DB-Anbieterassistent**. Jede Headerdatei enthält eine Zuordnung für die Eigenschaften in der OLE DB-Eigenschaftengruppe, die für das Objekt oder die in dieser Datei definierten Objekte definiert. Die Header-Datei, die das Datenquellenobjekt enthält enthält auch die eigenschaftenzuordnung für die [DataSource-Eigenschaften](https://msdn.microsoft.com/library/ms724188). `Session.h` enthält die eigenschaftenzuordnung für die [Sitzungseigenschaften](/previous-versions/windows/desktop/ms714221). Die Rowset- und Befehlsobjekte in einer einzigen Headerdatei, die aufgerufen werden *Projectname*RS.h. Diese Eigenschaften sind Mitglieder der [Rowseteigenschaften](/previous-versions/windows/desktop/ms711252) Gruppe.

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
