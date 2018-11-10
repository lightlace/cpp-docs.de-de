---
title: Isolated COM-Eigenschaften des Manifesttools (Visual C++)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
ms.openlocfilehash: 9eea3b2765bad6bd08cc9ee91a801e2b891511e5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50546518"
---
# <a name="isolated-com-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Isolated COM, Manifesttool, Konfigurationseigenschaften, &lt;Projektname&gt;-Eigenschaftenseiten (Dialogfeld)

Verwenden Sie dieses Dialogfeld, um **Isolated COM**-Optionen für die Datei [Mt.exe](https://msdn.microsoft.com/library/aa375649) anzugeben.

Öffnen Sie die Eigenschaftenseiten für Ihr Projekt oder Ihr Eigenschaftenblatt, um auf das Dialogfeld „Eigenschaftenseite“ zuzugreifen. Erweitern Sie den Knoten **Manifesttool** unter **Allgemeine Eigenschaften**, und klicken Sie dann auf **Isolated COM**.

## <a name="task-list"></a>Aufgabenliste

- [Vorgehensweise: Erstellen von isolierten Anwendungen zur Verwendung von COM-Komponenten](../build/how-to-build-isolated-applications-to-consume-com-components.md)

## <a name="uielement-list"></a>UIElement-Liste

- **Typbibliotheksdatei**

   Verwendet die Option „/tlb“, um den Namen der Typbibliotheksdatei (TLB-Datei) anzugeben, die das Manifesttool verwendet, um die Manifestdatei zu erstellen.

- **Registrierungsskriptdatei**

   Verwendet die Option „/rgs“, um den Namen der Registrierungsskriptdatei (RGS-Datei) anzugeben, die das Manifesttool verwendet, um die Manifestdatei zu erstellen.

- **Komponentendateiname**

   Verwendet die Option „/dll“, um den Namen der Ressource anzugeben, die das Manifesttool generiert. Sie müssen für diese Eigenschaft einen Wert eingeben, wenn Werte für die **Typbibliotheksdatei** oder die **Registrierungsskriptdatei** angegeben sind.

- **Ersetzungsdatei**

   Verwendet die Option „/replacements“, um den vollständigen Pfad zu der Datei anzugeben, die Werte für ersetzbare Zeichenfolgen in der RGS-Datei enthält.

## <a name="see-also"></a>Siehe auch

[Isolierte Anwendungen](/windows/desktop/SbsCs/isolated-applications)<br>
[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)