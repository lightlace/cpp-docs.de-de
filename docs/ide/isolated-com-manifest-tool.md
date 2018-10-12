---
title: Isolated COM-Eigenschaften des Manifesttools (Visual C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.RegistrarScriptFile
- VC.Project.VCManifestTool.ComponentFileName
- VC.Project.VCManifestTool.TypeLibraryFile
- VC.Project.VCManifestTool.ReplacementsFile
dev_langs:
- C++
ms.assetid: 457582b8-cfde-49c0-92e3-3a6b9e8c08eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cdb472ce082809a48dd3e42afd4481149eff3a28
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46407545"
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
[ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)