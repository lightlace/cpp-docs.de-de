---
title: Vom Anbieter-Assistenten generierte Dateien
ms.date: 10/18/2018
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
ms.openlocfilehash: c93618ebe9d3140864c2c47867ea970777c208b6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50580933"
---
# <a name="provider-wizard-generated-files"></a>Vom Anbieter-Assistenten generierte Dateien

Die **ATL-OLE DB-Anbieter-Assistenten** generiert die folgenden Dateien. In den folgenden Themen verwenden Sie den kurzen Namen *benutzerdefinierte*, aber die exakten Dateinamen hängt die Wahl, die Sie vorgenommen haben, wenn Sie den Anbieter zu erstellen.

|Dateiname|Beschreibung|
|---------------|-----------------|
|*Benutzerdefinierte*RS.cpp|Der Befehl-Hilfe enthält `Execute` -Methode und die Anbieter-Spalte-Zuordnung.|
|*Benutzerdefinierte*DS.h|Implementiert das Datenquellenobjekt. Diese Headerdatei enthält die eigenschaftenzuordnung für die Eigenschaften der Datenquelle.|
|*Benutzerdefinierte*RS.h|Implementiert die Befehls- und Rowsetobjekte-Objekte. Diese Headerdatei enthält die eigenschaftenzuordnung Rowset- und Eigenschaften.|
|*Benutzerdefinierte*Sess.h|Implementiert das Session-Objekt. Diese Headerdatei enthält die eigenschaftenzuordnung für die Eigenschaften der leistungssitzung aus.|
|*Benutzerdefinierte*RGS|Enthält die registrierten Objekte generiert, indem die **OLE DB-Anbieterassistent**.|

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)<br/>
