---
title: Vom Anbieter-Assistenten generierte Dateien
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: de5c9056402cb1db25240772eb3c592523daafae
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525325"
---
# <a name="provider-wizard-generated-files"></a>Vom Anbieter-Assistenten generierte Dateien

::: moniker range="vs-2019"

Der ATL-OLE DB-Anbieter-Assistent ist in Visual Studio 2019 und höher nicht verfügbar.

::: moniker-end

::: moniker range="vs-2017"

Der **ATL-OLE DB-Anbieter-Assistent** generiert die folgenden Dateien. Die folgenden Themen verwenden den Custom *Benutzerdefiniert*, aber die genauen Dateinamen hängen von der Wahl ab, die Sie beim Anlegen des Anbieters getroffen haben.

|Dateiname|Beschreibung|
|---------------|-----------------|
|*Custom*RS.cpp|Enthält die `Execute`-Hilfsmethode für den Befehl und die Spaltenzuordnung für den Anbieter.|
|*Custom*DS.h|Implementiert das Datenquellenobjekt. Diese Headerdatei enthält die Eigenschaftenzuordnung für die Eigenschaften der Datenquelle.|
|*Custom*RS.h|Implementiert die Befehls- und Rowsetobjekte. Diese Headerdatei enthält die Eigenschaftenzuordnung für Rowset- und Befehlseigenschaften.|
|*Custom*Sess.h|Implementiert das Sitzungsobjekt. Diese Headerdatei enthält die Eigenschaftenzuordnung für die Sitzungseigenschaften.|
|*Custom*.rgs|Enthält die vom **ATL-OLE DB-Anbieter-Assistenten** generierten registrierten Objekte.|

::: moniker-end

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)<br/>
