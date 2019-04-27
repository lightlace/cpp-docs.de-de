---
title: DCOMCNFG
ms.date: 11/04/2016
helpviewer_keywords:
- DCOMCNFG utility
- DCOM, configuring in ATL
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
ms.openlocfilehash: a389a46cd02b40cef46d687743fd3416cc4f3154
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250783"
---
# <a name="dcomcnfg"></a>DCOMCNFG

DCOMCNFG ist ein Windows NT 4.0-Hilfsprogramm, das Ihnen ermöglicht, die verschiedene DCOM-spezifischen Einstellungen in der Registrierung zu konfigurieren. Das Fenster "DCOMCNFG" verfügt über drei Seiten: Standardsicherheit, Eigenschaften und Anwendungen. Unter Windows 2000 ist eine vierte Seite Standardprotokolle, vorhanden.

## <a name="default-security-page"></a>Standard-Seite "Sicherheit"

Die Standardsicherheit-Seite können Sie die Standardberechtigungen für Objekte im System an. Die Seite "Sicherheit standardmäßig" besteht aus drei Abschnitten: Zugriff, Start und Konfiguration. Um einen Abschnitt mit den Standardeinstellungen zu ändern, klicken Sie auf den entsprechenden **Standard bearbeiten** Schaltfläche. Diese Default Security-Einstellungen werden gespeichert, in der Registrierung unter `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.

## <a name="default-protocols-page"></a>Seite "Standardprotokolle"

Diese Seite enthält den Satz von Netzwerkprotokollen für DCOM auf diesem Computer verfügbar. Die Reihenfolge entspricht, die Priorität an, in der sie verwendet werden; die erste in der Liste hat die höchste Priorität. Protokolle können hinzugefügt oder gelöscht werden, auf dieser Seite werden.

## <a name="default-properties-page"></a>Standard-Eigenschaftenseite

Sie müssen auf der Seite Eigenschaften der Standard-auswählen der **Distributed COM auf diesem Computer aktivieren** Kontrollkästchen, wenn von Clients auf anderen Computern zum Zugreifen auf COM-Objekte, die auf diesem Computer ausgeführt werden soll. Wählen diese Option wird die `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` Wert `Y`.

## <a name="applications-page"></a>Seite "Anwendungen"

Sie ändern die Einstellungen für ein bestimmtes Objekt der Seite "Anwendungen". Wählen Sie einfach die Anwendung aus der Liste und klicken Sie auf die **Eigenschaften** Schaltfläche. Das Fenster "Eigenschaften" umfasst fünf Seiten:

- Die Seite "Allgemein" wird die Anwendung, mit denen, der Sie arbeiten werden, bestätigt.

- Die Seite "Speicherort" können Sie angeben, in dem die Anwendung ausgeführt werden soll, wenn ein Client aufruft `CoCreateInstance` auf die relevanten CLSID. Bei Auswahl der **führen Sie die Anwendung auf dem folgenden Computer** Kontrollkästchen, und geben Sie einen Computernamen ein `RemoteServerName` Wert wird unter die App-ID für diese Anwendung hinzugefügt. Löschen der **führen Sie die Anwendung auf diesem Computer** Kontrollkästchen umbenennungen der `LocalService` Wert `_LocalService` und dadurch deaktiviert.

- Die Seite "Sicherheit" ähnelt der Seite "Sicherheit Standard" finden Sie im Fenster "DCOMCNFG" mit dem Unterschied, dass diese Einstellungen nur für die aktuelle Anwendung gelten. In diesem Fall werden die Einstellungen der App-ID für dieses Objekt gespeichert.

- Die Seite identifizieren identifiziert, welcher Benutzer verwendet wird, um die Anwendung auszuführen.

- Seite "Endpunkte" enthält die Protokolle und Endpunkte für die Verwendung von Clients von der ausgewählten DCOM-Server verfügbar.

## <a name="see-also"></a>Siehe auch

[Dienste](../atl/atl-services.md)
