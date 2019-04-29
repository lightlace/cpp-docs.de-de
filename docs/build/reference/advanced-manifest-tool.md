---
title: Erweitert, Manifesttool, Konfigurationseigenschaften, &lt;Projektname > Eigenschaftenseiten (Dialogfeld)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCManifestTool.KeyFile
- VC.Project.VCManifestTool.UpdateFileHashes
- VC.Project.VCManifestTool.UpdateFileHashesSearchPath
- VC.Project.VCManifestTool.ValidateSignature
- VC.Project.VCManifestTool.KeyContainer
ms.assetid: 3d587366-05ea-4956-a978-313069660735
ms.openlocfilehash: a20e474deb69099c53ad656dda5406e7161a1695
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295136"
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
[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br>
[Manifesttool-Eigenschaftenseiten](manifest-tool-property-pages.md)<br>
[Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio](../working-with-project-properties.md)
