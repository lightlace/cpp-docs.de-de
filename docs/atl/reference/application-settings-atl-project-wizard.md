---
title: Anwendungseinstellungen, ATL-Projekt-Assistent | Microsoft Docs
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
ms.openlocfilehash: 47fbf95451834e5f8c41e8b6d7e5af7a9746bb85
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357404"
---
# <a name="application-settings-atl-project-wizard"></a>Anwendungseinstellungen, ATL-Projekt-Assistent
Verwenden der **Anwendungseinstellungen** Seite des ATL-Projekt-Assistenten entworfen und grundlegende Funktionen zu einem neuen ATL-Projekt hinzufügen.  
  
## <a name="server-type"></a>Servertyp  
 Wählen Sie eine der drei Servertypen:  
  
 **Dynamic Link Library (DLL)**  
 Wählen Sie zum Erstellen von in-Process-Server.  
  
 **Ausführbare Datei (EXE)**  
 Wählen Sie einen lokalen Out-of-Process-Server erstellen. Diese Option lässt keine Unterstützung für MFC oder COM+ 1.0. Es ist nicht gestattet, das Zusammenführen von Proxy/Stub-Code.  
  
 **Dienst (EXE)**  
 Wählen Sie eine Windows-Anwendung erstellen, die im Hintergrund ausgeführt, beim Starten von Windows wird. Diese Option lässt keine Unterstützung für MFC oder COM+ 1.0 oder das Zusammenführen von Proxy/Stub-Code nicht zugelassen.  
  
## <a name="additional-options"></a>Zusätzliche Optionen  
  
> [!NOTE]
>  Alle zusätzlichen Optionen sind für nur für DLL-Projekte verfügbar.  
  
 **Zulassen Sie Zusammenführen von Proxy/Stub code**  
 Wählen Sie die **ermöglichen das Zusammenführen von Code Proxy/Stub** Kontrollkästchen einen Schlüsselverweis beim Marshallen von Schnittstellen erforderlich ist. Diese Option setzt die MIDL-generierten Proxy und Stub-Code in derselben ausführbaren Datei, wie der Server.  
  
 **MFC-Unterstützung**  
 Wählen Sie, um anzugeben, dass das Objekt MFC-Unterstützung umfasst. Diese Option wird das Projekt auf die MFC-Bibliotheken verknüpft, damit Sie auf alle Klassen und die darin enthaltenen Funktionen zugreifen können.  
  
 **COM+ 1.0-Unterstützung**  
 Wählen Sie zum Ändern der Projekt-Buildeinstellungen so, dass COM+ 1.0 Komponenten unterstützen. Zusätzlich zu den standardmäßigen Liste der Bibliotheken fügt der Assistent die COM+ 1.0 komponentenspezifische Bibliothek comsvcs.lib hinzu:  
  
 Darüber hinaus ist die mtxex.dll Verzögerung, die auf dem Hostsystem geladen werden, wenn die Anwendung gestartet wird.  
  
-   **Unterstützt die Registrierung der Komponente** Projektsprache ATL-Unterstützung für COM+ 1.0 Komponenten enthält, können Sie diese Option festlegen. Die Registrierung der Komponente ermöglicht das COM+ 1.0-Objekt, rufen Sie eine Liste der Komponenten, Komponenten registrieren oder Aufheben der Registrierung Komponenten (einzeln oder alle auf einmal).  
  
## <a name="see-also"></a>Siehe auch  
 [ATL-Projekt-Assistent](../../atl/reference/atl-project-wizard.md)   
 [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md)   
 [Standardmäßige ATL-Projektkonfigurationen](../../atl/reference/default-atl-project-configurations.md)

