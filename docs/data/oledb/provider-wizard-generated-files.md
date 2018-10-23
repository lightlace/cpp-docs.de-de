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
ms.openlocfilehash: f22c5e21d1f648a8235207713391306b24e0a6cf
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49807289"
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