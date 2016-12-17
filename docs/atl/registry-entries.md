---
title: "Registry Entries"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Registrierung, application IDs"
  - "Registrierung, ATL services entries"
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Registry Entries
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM wurde das Konzept von Anwendungs\-IDs \(AppIDs\) vor, die Konfigurationsoptionen für eine oder mehrere DCOM\-Objekte in einen zentralen Ort in der Registrierung gruppieren.  Sie geben ein AppID\-Element an, indem Sie den Wert im benannten AppID\-Element Wert unter CLSID des Objekts angeben.  
  
 Standardmäßig verwendet ein ATL\-generierter Dienst CLSID sein als die GUID für AppID\-Element sein.  Die `HKEY_CLASSES_ROOT\AppID` können Sie DCOM\-Besondere Einträge angeben.  Zunächst sind zwei Einträge:  
  
-   `LocalService`, mit einem Wert gleich den Namen des Diensts.  Wenn dieser Wert vorhanden ist, wird er statt der `LocalServer32` Schlüssel unter CLSID verwendet.  
  
-   `ServiceParameters`, mit einem Wert gleich `–Service`.  Dieser Wert gibt Parameter an, die an den Dienst übergeben werden, wenn er gestartet wird.  Beachten Sie dass diese Parameter werden an die `ServiceMain`\-Funktion des Diensts, nicht `WinMain`.  
  
 Jeder DCOM\-Dienst muss auch eine andere Schlüssel mit `HKEY_CLASSES_ROOT\AppID` erstellen.  Dieser Schlüssel ist gleich dem Namen der EXE\-Datei und fungiert als Querverweis auf, da sie einen AppID\-Wert enthält, der zurück an den AppID\-Einträgen zeigt.  
  
## Siehe auch  
 [Dienste](../atl/atl-services.md)