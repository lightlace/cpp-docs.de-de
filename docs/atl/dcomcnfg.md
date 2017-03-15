---
title: "DCOMCNFG | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DCOMCNFG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DCOM, configuring in ATL"
  - "DCOMCNFG utility"
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DCOMCNFG
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**DCOMCNFG** ist ein Windows NT 4.0\-Hilfsprogramm, das Ihnen ermöglicht, verschiedene DCOM\-Besondere Einstellungen in der Registrierung zu konfigurieren.  Das **DCOMCNFG** Fenster hat drei Seiten: Standard Sicherheit, Standardeigenschaften und Anwendungen.  Unter Windows 2000 ist eine vierte Seite, Standard\-Protokolle, vorhanden.  
  
## Standard Sicherheits\-Seite  
 Sie können die standardmäßige Sicherheitsseite verwenden, um Standardberechtigungen für Objekte auf dem System anzugeben.  Die standardmäßige Sicherheitsseite hat drei Abschnitte: Zugriff, Starten und Konfiguration.  Um die Standardeinstellungen eines Abschnitts zu ändern, klicken Sie auf die entsprechende Schaltfläche **Edit Default**.  Diese Standardsicherheitseinstellungen werden in der Registrierung unter `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE` gespeichert.  
  
## Standard\-Protokoll\-Seite  
 Diese Seite zeigt den von Netzwerkprotokollen auf, die zu DCOM auf diesem Computer verfügbar sind.  Die Reihenfolge spiegelt die Priorität, in der sie verwendet werden; das erste in der Liste hat die höchste Priorität.  Protokolle können von dieser Seite hinzugefügt oder gelöscht werden.  
  
## Standardeigenschafts\-Seite  
 Auf den Standardeigenschaften Seite, müssen Sie das **Enable Distributed COM on this computer** Kontrollkästchen aktivieren, wenn Sie die Clients auf anderen Computern auf COM\-Objekte zugreifen soll die auf diesen Computer.  Das Auswählen dieser Option wird den `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM`\-Wert zu `Y` fest.  
  
## Anwendungsseite  
 Sie ändern die Einstellungen für ein bestimmtes Objekt mit der Anwendungsseite.  Wählen Sie die Anwendung einfach aus der Liste aus und klicken Sie auf die Schaltfläche **Eigenschaften**.  Das Eigenschaftenfenster verfügt über fünf Seiten:  
  
-   Die allgemeine Seite bestätigt die Anwendung, mit der Sie arbeiten.  
  
-   Die Speicherortseite ermöglicht es Ihnen, um anzugeben, wo die Anwendung ausgeführt werden soll, wenn ein Client `CoCreateInstance` auf dem relevanten CLSID aufruft.  Wenn Sie das Kontrollkästchen **Anwendung auf dem folgenden Computer ausführen** eingeben und einen Computernamen auswählen, wird ein `RemoteServerName`\-Wert unter dem AppID für diese Anwendung hinzugefügt.  Das **Anwendung auf diesem Computer ausführen** Kontrollkästchen Löschen, benennt den `LocalService`\-Wert zu `_LocalService` deaktiviert und ihn so.  
  
-   Die Seite Sicherheit ist in die Sicherheitsseite vergleichbar, die im **DCOMCNFG** Fenster gefunden wird, dass diese Einstellungen gelten nur für die aktuelle Anwendung zu.  Auch hier werden die Einstellungen unter dem AppID für dieses Objekt gespeichert.  
  
-   Die Bestimmungsseite identifiziert, welcher Benutzer verwendet wird, um die Anwendung auszuführen.  
  
-   Die Endpunktseite zeigt den Satz von Protokollen und Endpunkten auf, die für Clients des ausgewählten DCOM\-Servers verfügbar sind.  
  
## Siehe auch  
 [Dienste](../atl/atl-services.md)