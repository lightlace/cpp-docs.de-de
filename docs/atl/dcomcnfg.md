---
title: DCOMCNFG | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DCOMCNFG
dev_langs: C++
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bffed7658232d11dd7741900d6eca14de341e855
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="dcomcnfg"></a>DCOMCNFG
**DCOMCNFG** ist ein Windows NT 4.0-Hilfsprogramm, das Ihnen ermöglicht, die verschiedene DCOM-spezifische Einstellungen in der Registrierung zu konfigurieren. Die **DCOMCNFG** Fenster hat drei Seiten: Default Security Standardeigenschaften und Anwendungen. Unter Windows 2000 ist eine vierte Seite Standardprotokolle vorhanden.  
  
## <a name="default-security-page"></a>Standard-Seite "Sicherheit"  
 Die Standardsicherheit-Seite können Sie die Standardberechtigungen für Objekte auf dem System angeben. Die Seite "Sicherheit standardmäßig" besteht aus drei Abschnitten: Zugriff, Start und Konfiguration. Um einen Abschnitt Standardwerte zu ändern, klicken Sie auf den entsprechenden **Standard bearbeiten** Schaltfläche. Diese Standard-Sicherheitseinstellungen werden gespeichert, in der Registrierung unter `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.  
  
## <a name="default-protocols-page"></a>Standardseite "Protokolle"  
 Diese Seite enthält den Satz von Netzwerkprotokollen für DCOM auf diesem Computer verfügbar. Die Reihenfolge wiedergibt, die Priorität an, in der sie verwendet werden sollen; die erste Aufgabe in der Liste hat die höchste Priorität. Protokolle können hinzugefügt oder aus dieser Seite gelöscht werden.  
  
## <a name="default-properties-page"></a>Standardseite "Eigenschaften"  
 Sie müssen auf der Seite "Standardeigenschaften" Auswählen der **aktivieren (Distributed COM) auf diesem Computer** das Kontrollkästchen, wenn Clients auf anderen Computern zum Zugreifen auf COM-Objekte, die auf diesem Computer ausgeführt werden soll. Wählen diese Option wird die `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` Wert `Y`.  
  
## <a name="applications-page"></a>Seite "Anwendungen"  
 Sie ändern die Einstellungen für ein bestimmtes Objekt mit der Seite "Anwendungen". Wählen Sie zuerst die Anwendung aus der Liste und klicken Sie auf die **Eigenschaften** Schaltfläche. Das Eigenschaftenfenster hat fünf Seiten:  
  
-   Die Seite "Allgemein" bestätigt die Anwendung, mit dem Sie arbeiten.  
  
-   Die Seite "Speicherort" können Sie angeben, in dem die Anwendung ausgeführt werden soll, wenn ein Client aufruft `CoCreateInstance` auf die relevanten CLSID. Bei Auswahl der **führen Sie die Anwendung auf die folgenden Computer** Kontrollkästchen und geben Sie einen Computernamen ein `RemoteServerName` Wert unter der AppID der Anwendung hinzugefügt wird. Deaktivieren der **führen Sie die Anwendung auf diesem Computer** benennt das Kontrollkästchen der `LocalService` Wert `_LocalService` und somit wird deaktiviert.  
  
-   Die Seite "Sicherheit" ähnelt der Default-Security Seite, in gefunden der **DCOMCNFG** Fenster, mit dem Unterschied, dass diese Einstellungen nur für die aktuelle Anwendung gelten. Die Einstellungen werden erneut aus, unter der AppID für dieses Objekt gespeichert.  
  
-   Die Seite identifizieren identifiziert, die der Benutzer verwendet wird, um die Anwendung auszuführen.  
  
-   Seite "Endpunkte" werden die Protokolle und Endpunkte für die Verwendung durch Clients des ausgewählten DCOM-Servers zur Verfügung.  
  
## <a name="see-also"></a>Siehe auch  
 [Dienste](../atl/atl-services.md)

