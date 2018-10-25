---
title: Anbieter-Assistenten generierte Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, wizard-generated files
ms.assetid: 6e1ac94b-eb90-4abf-82b3-06944b947ebc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a9bc7c85dccdfe095412450d5020fc8a6b42d516
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50076970"
---
# <a name="provider-wizard-generated-files"></a>Vom Anbieter-Assistenten generierte Dateien

Der ATL-OLE DB-Anbieter-Assistent generiert die folgenden Dateien. In den folgenden Themen verwenden Sie den kurzen Namen *benutzerdefinierte*, aber die exakten Dateinamen hängt die Wahl, die Sie vorgenommen haben, wenn Sie den Anbieter zu erstellen.

|Dateiname|Beschreibung|
|---------------|-----------------|
|*Benutzerdefinierte*RS.cpp|Der Befehl-Hilfe enthält `Execute` -Methode und die Anbieter-Spalte-Zuordnung.|
|*Benutzerdefinierte*DS.h|Implementiert das Datenquellenobjekt. Diese Headerdatei enthält die eigenschaftenzuordnung für die Eigenschaften der Datenquelle.|
|*Benutzerdefinierte*RS.h|Implementiert die Befehls- und Rowsetobjekte-Objekte. Diese Headerdatei enthält die eigenschaftenzuordnung Rowset- und Eigenschaften.|
|*Benutzerdefinierte*Sess.h|Implementiert das Session-Objekt. Diese Headerdatei enthält die eigenschaftenzuordnung für die Eigenschaften der leistungssitzung aus.|
|*Benutzerdefinierte*RGS|Enthält die registrierten Objekte, die vom OLE DB-Anbieter-Assistenten generiert.|

## <a name="see-also"></a>Siehe auch

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)