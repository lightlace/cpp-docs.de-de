---
title: Anbieter-Assistenten generierte Dateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 26e20e0417e2253158930a8d3d055171fe767001
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108403"
---
# <a name="provider-wizard-generated-files"></a>Vom Anbieter-Assistenten generierte Dateien

Der ATL-OLE DB-Anbieter-Assistent generiert die folgenden Dateien. In den folgenden Themen verwenden Sie den kurzen Namen "Meinanbieter", aber die exakten Dateinamen hängt die Wahl, die Sie vorgenommen werden, wenn Sie den Anbieter zu erstellen.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|MyProviderRS.cpp|Der Befehl-Hilfe enthält `Execute` -Methode und die Anbieter-Spalte-Zuordnung.|  
|MyProviderDS.h|Implementiert das Datenquellenobjekt. Diese Headerdatei enthält die eigenschaftenzuordnung für die Eigenschaften der Datenquelle.|  
|MyProviderRS.h|Implementiert die Befehls- und Rowsetobjekte-Objekte. Diese Headerdatei enthält die eigenschaftenzuordnung Rowset- und Eigenschaften.|  
|MyProviderSess.h|Implementiert das Session-Objekt. Diese Headerdatei enthält die eigenschaftenzuordnung für die Eigenschaften der leistungssitzung aus.|  
|MyProvider.rgs|Enthält die registrierten Objekte, die vom OLE DB-Anbieter-Assistenten generiert.|  
  
## <a name="see-also"></a>Siehe auch  

[Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)