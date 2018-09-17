---
title: Anwendungseinstellungen, ATL-Projekt-Assistent | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.atl.com.appset
dev_langs:
- C++
helpviewer_keywords:
- ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 49e25fa8a730ea31caf747d07ce30a0622c4bd01
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45714687"
---
# <a name="application-settings-atl-project-wizard"></a>Anwendungseinstellungen, ATL-Projekt-Assistent

Verwenden der **Anwendungseinstellungen** Seite des Assistenten die ATL-Projekt zum Entwerfen und zu grundlegende Funktionen zu einem neuen ATL-Projekt hinzufügen.

## <a name="server-type"></a>Servertyp

Wählen Sie aus einer von drei Server:

- **Dynamic Link Library (DLL)**  

   Wählen Sie zum Erstellen von in-Process-Server.

- **Ausführbare Datei (EXE)**  

   Wählen Sie einen lokalen Out-of-Process-Server erstellen. Diese Option lässt keine Unterstützung für MFC oder COM+ 1.0 zu. Es lässt sich nicht für das Zusammenführen von Proxy/Stub-Code.

- **Dienst (EXE)**  

   Wählen Sie zum Erstellen einer Windows-Anwendung, die im Hintergrund ausgeführt wird, wenn Windows gestartet wird. Diese Option lässt sich nicht auf die Unterstützung für MFC oder COM+ 1.0 oder das Zusammenführen von Proxy/Stub-Code nicht zulässig.

## <a name="additional-options"></a>Zusätzliche Optionen

> [!NOTE]
> Alle zusätzlichen Optionen sind für die nur für DLL-Projekten verfügbar.

- **Zulassen Sie Zusammenführen von Proxy-/ Stubcode**  

   Wählen Sie die **Zusammenführen von Proxy-/ Stubcode zulassen** Kontrollkästchen Speicherschemamappings beim Marshallen von Schnittstellen erforderlich ist. Diese Option setzt den MIDL-generierten Proxy und Stub-Code in der gleichen ausführbare Datei als dem Server.

- **MFC-Unterstützung**  

   Wählen Sie an, dass das Objekt die MFC-Unterstützung enthält. Diese Option wird das Projekt mit der MFC-Bibliotheken verknüpft, damit Sie auf alle Klassen und Funktionen, die darin enthaltenen zugreifen können.

- **COM+ 1.0-Unterstützung**  

   Wählen Sie diese Option ändern Sie das Projekt erstellen Einstellungen zur Unterstützung von COM+ 1.0-Komponenten. Zusätzlich zu den standardmäßigen Bibliotheken fügt der Assistent für die COM+ 1.0 Komponenten-spezifischen Bibliothek comsvcs.lib hinzu:

   Darüber hinaus ist die mtxex.dll Verzögerung, die auf dem Hostsystem geladen wird, wenn die Anwendung gestartet wird.

- **Registrierung der Komponente unterstützt**

   Wenn Ihr ATL-Projekt Unterstützung für COM+ 1.0 Komponenten enthält, können Sie diese Option festlegen. Die Registrierung der Komponente können das COM+ 1.0-Objekt zum Abrufen einer Liste von Komponenten, Komponenten registrieren oder Aufheben der Registrierung Komponenten (einzeln oder alle auf einmal).

## <a name="see-also"></a>Siehe auch

[ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
[Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)   
[Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

