---
title: Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projektname&gt;-Eigenschaftenseiten“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
dev_langs:
- C++
ms.assetid: 3d587366-05ea-4956-a978-313069660735
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e44ba6065658c085777ada39f75bd5fa1cdc2fb
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382946"
---
# <a name="advanced-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Erweitert, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projektname&gt;-Eigenschaftenseiten“

Verwenden Sie dieses Dialogfeld, um erweiterte Optionen für die Datei [Mt.exe](https://msdn.microsoft.com/library/aa375649) anzugeben.

Öffnen Sie die Eigenschaftenseiten für Ihr Projekt oder Ihr Eigenschaftenblatt, um auf das Dialogfeld „Eigenschaftenseite“ zuzugreifen. Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und klicken Sie dann auf **Erweitert**.

## <a name="uielement-list"></a>UIElement-Liste

- **Dateihashes aktualisieren**

   Verwenden Sie die Option „/hashupdate“, um anzugeben, dass das Manifesttool den Hashwert der in den `<file>`-Elementen angegebenen Dateien berechnet, und aktualisieren Sie dann die Hashattribute mit dem berechneten Wert.

- **Suchpfad für Dateihashes aktualisieren**

   Gibt den Suchpfad für Dateien an, auf die in `<file>`-Elementen verwiesen wird. Diese Option verwendet auch die Option „/hashupdate“.

## <a name="see-also"></a>Siehe auch

[\<file> Element](/visualstudio/deployment/file-element-clickonce-application)<br>
[ClickOnce-Anwendungsmanifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)<br>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)