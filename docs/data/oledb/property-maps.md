---
title: Eigenschaftenzuordnungen
ms.date: 10/24/2018
helpviewer_keywords:
- OLE DB providers, properties
- maps, property
- property maps
ms.assetid: 44abde56-90ad-4612-854e-d2fa5426fa80
ms.openlocfilehash: 9df98dc85c9242693319542cea0730341d87a052
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62284032"
---
# <a name="property-maps"></a>Eigenschaftenzuordnungen

Die Sitzung, Rowset und optional Command-Objekt unterstützt jeder Anbieter eine oder mehrere Eigenschaften. Diese Eigenschaften werden in der eigenschaftenzuordnungen, die in den Headerdateien, die von erstellten gespeicherten definiert die **OLE DB-Anbieterassistent**. Jede Headerdatei enthält eine Zuordnung für die Eigenschaften in der OLE DB-Eigenschaftengruppe, die für das Objekt oder die in dieser Datei definierten Objekte definiert. Die Header-Datei, die das Datenquellenobjekt enthält enthält auch die eigenschaftenzuordnung für die [DataSource-Eigenschaften](https://msdn.microsoft.com/library/ms724188). `Session.h` enthält die eigenschaftenzuordnung für die [Sitzungseigenschaften](/previous-versions/windows/desktop/ms714221(v=vs.85)). Die Rowset- und Befehlsobjekte in einer einzigen Headerdatei, die aufgerufen werden *Projectname*RS.h. Diese Eigenschaften sind Mitglieder der [Rowseteigenschaften](/previous-versions/windows/desktop/ms711252(v=vs.85)) Gruppe.

## <a name="see-also"></a>Siehe auch

[Architektur von OLE DB-Anbietervorlagen](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
