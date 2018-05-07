---
title: Anbieter-Assistenten generierte Dateien | Microsoft Docs
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
ms.openlocfilehash: ac23f06bf1ae697ecd627d493aa5902219488138
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="provider-wizard-generated-files"></a>Vom Anbieter-Assistenten generierte Dateien
Der ATL-OLE DB-Anbieter-Assistent generiert die folgenden Dateien. Verwenden Sie in den folgenden Themen des kurzen Namens "MyProvider", aber die genauen Dateinamen hängt die Wahl, die Sie beim Erstellen des Anbieters vorgenommen.  
  
|Dateiname|Beschreibung|  
|---------------|-----------------|  
|MyProviderRS.cpp|Enthält den Befehl Helper `Execute` -Methode und der Anbieter-spaltenzuordnung.|  
|MyProviderDS.h|Implementiert das Datenquellenobjekt. Diese Headerdatei enthält die eigenschaftenzuordnung für Eigenschaften der Datenquelle.|  
|MyProviderRS.h|Implementiert die Befehls- und Rowsetobjekte-Objekte. Diese Headerdatei enthält die eigenschaftenzuordnung für Eigenschaften von Rowset- und Befehlsobjekte.|  
|MyProviderSess.h|Implementiert das Sitzungsobjekt. Diese Headerdatei enthält die eigenschaftenzuordnung für Sitzungseigenschaften.|  
|MyProvider.rgs|Enthält die registrierten Objekte, die vom OLE DB-Anbieter-Assistenten generiert.|  
  
## <a name="see-also"></a>Siehe auch  
 [Erstellen eines OLE DB-Anbieters](../../data/oledb/creating-an-ole-db-provider.md)