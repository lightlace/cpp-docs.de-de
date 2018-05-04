---
title: Registrierungseinträge (ATL) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL services entries
- registry, application IDs
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ac8e202fc2fc3d58e2d57a9fbfa15264d9fd310e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="registry-entries"></a>Registrierungseinträge
DCOM eingeführt, das Konzept der Anwendungs-IDs (AppIDs), welcher Gruppe von Konfigurationsoptionen für eine oder mehrere DCOM-Objekte in einem zentralen Ort in der Registrierung. Sie geben eine AppID, der angibt, dessen Werts in der AppID benannten Wert unter der CLSID des Objekts.  
  
 Standardmäßig verwendet ein ATL-generierter Dienst als GUID seines CLSID für die AppID an. Unter `HKEY_CLASSES_ROOT\AppID`, können Sie die DCOM-spezifische Einträge angeben. Zu Beginn sind zwei Einträge vorhanden:  
  
-   `LocalService`, mit einem Wert, der gleich dem Namen des Diensts. Wenn dieser Wert vorhanden ist, wird Sie anstelle von verwendet die `LocalServer32` Schlüssel unter der CLSID.  
  
-   `ServiceParameters`, mit einem Wert, der gleich `-Service`. Dieser Wert gibt die Parameter, die an den Dienst übergeben werden, wenn sie gestartet wird. Beachten Sie, die diese Parameter an des Diensts übergeben werden `ServiceMain` funktionieren, nicht `WinMain`.  
  
 DCOM-Dienst muss außerdem erstellen Sie einen weiteren Schlüssel unter `HKEY_CLASSES_ROOT\AppID`. Dieser Schlüssel ist identisch mit dem Namen der EXE-Datei und fungiert als ein Querverweis, da sie einen AppID-Wert wieder auf die AppID-Einträge enthält.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)

