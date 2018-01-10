---
title: Anwendungseinstellungen, ATL-Projekt-Assistent | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.atl.com.appset
dev_langs: C++
helpviewer_keywords: ATL Project Wizard, application settings
ms.assetid: d48c9fc5-f439-49fd-884c-8bcfa7d52991
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 12b7e383716d7cfa330bdfdebe21c33550669cc2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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

