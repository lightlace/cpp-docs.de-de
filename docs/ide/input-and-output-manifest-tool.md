---
title: Eingabe- und Ausgabeeigenschaften des Manifesttools (Visual C++)
ms.date: 08/27/2018
f1_keywords:
- VC.Project.VCManifestTool.OutputManifestFile
- VC.Project.VCManifestTool.InputResourceManifests
- VC.Project.VCManifestTool.EmbedManifest
- VC.Project.VCManifestTool.AdditionalManifestFiles
- VC.Project.VCManifestTool.DependencyInformationFile
- VC.Project.VCManifestTool.OutputResourceManifest
- VC.Project.VCManifestTool.GenerateCatalogFiles
ms.assetid: a8bb20f6-7ace-45ca-bab0-b4f4a5caf170
ms.openlocfilehash: 7b9af50e6dca2dafa4dabd356a868405dfacc958
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741187"
---
# <a name="input-and-output-manifest-tool-configuration-properties-ltprojectnamegt-property-pages-dialog-box"></a>Eingabe und Ausgabe, Manifesttool, Konfigurationseigenschaften, Dialogfeld „&lt;Projektname&gt;-Eigenschaftenseiten“

Verwenden Sie dieses Dialogfeld, um Eingabe- und Ausgabeoptionen für die Datei [Mt.exe](/windows/desktop/SbsCs/mt-exe) anzugeben.

Öffnen Sie die Eigenschaftenseiten für Ihr Projekt oder Ihr Eigenschaftenblatt, um auf das Dialogfeld „Eigenschaftenseite“ zuzugreifen. Erweitern Sie den Knoten **Manifesttool** unter **Konfigurationseigenschaften**, und klicken Sie dann auf **Eingabe und Ausgabe**.

## <a name="uielement-list"></a>UIElement-Liste

**Zusätzliche Manifestdateien**<br/>
Verwendet die Option **/manifest**, um die vollständigen Pfade von zusätzlichen Manifestdateien anzugeben, die das Manifesttool verarbeitet oder zusammenführt. Vollständige Pfade werden durch Semikolons getrennt.

**Ressourcenmanifeste eingeben**<br/>
Verwendet die Option **/inputresource**, um den vollständigen Pfad einer Ressource vom Typ RT_MANIFEST anzugeben, die in das Manifesttool eingegeben wird. Dem Pfad kann die angegebene Ressourcen-ID folgen. Beispiel:

`dll_with_manifest.dll;#1`

Die Ressourcen-ID ist optional und lautet standardmäßig CREATEPROCESS_MANIFEST_RESOURCE_ID in „winuser.h“.

**Manifest einbetten**<br/>
- **Ja** gibt an, dass das Projektsystem die Anwendungsmanifestdatei in die Assembly einbettet.

- **Nein** gibt an, dass das Projektsystem die Anwendungsmanifestdatei als eigenständige Datei erstellt.

**Manifestdatei ausgeben**<br/>
Gibt den Namen der Ausgabemanifestdatei an. Diese Eigenschaft ist optional, wenn nur eine Manifestdatei mit dem Manifesttool bearbeitet wird.

**Manifestressourcendatei**<br/>
Gibt die Ausgaberessourcendateien an, die verwendet werden, um das Manifest in die Projektausgabe einzubetten.

**Katalogdateien generieren**<br/>
Verwendet die Option **/makecdfs**, um anzugeben, dass das Manifesttool die Katalogdefinitionsdateien (CDF-Dateien) generiert, die zum Erstellen von Katalogen verwendet werden.

**Manifest aus einer verwalteten Assembly generieren**<br/>
Generiert ein Manifest aus einer verwalteten Assembly. (**-managedassemblyname:**<em>Datei</em>).

**Abhängigkeitselement unterdrücken**<br/>
Wird mit der Option **-managedassembly** verwendet. Dieses Tag unterdrückt die Generierung von Abhängigkeitselementen im endgültigen Manifest.

**Kategorietags generieren**<br/>
Wird mit der Option **-managedassembly** verwendet. Durch dieses Tag werden die Kategorietags generiert.

**DPI aktivieren**<br/>
Gibt an, ob die Anwendung DPI-fähig ist. Für MFC-Projekte ist diese Einstellung standardmäßig auf **Ja** festgelegt, andernfalls ist **Nein** festgelegt, da nur MFC-Projekte über integrierte DPI-Unterstützung verfügen. Sie können die Einstellung auf **Ja** festlegen, indem Sie Code hinzufügen, um verschiedene DPI-Einstellungen zu verarbeiten. Wenn Sie Ihre Anwendung auf DPI-fähig einstellen und sie nicht DPI-fähig ist, wird sie möglicherweise verschwommen oder klein angezeigt.

## <a name="see-also"></a>Siehe auch

[ClickOnce Application Manifest](/visualstudio/deployment/clickonce-application-manifest)<br/>
[Manifesttool-Eigenschaftenseiten](../ide/manifest-tool-property-pages.md)<br/>
[Arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md)<br/>
