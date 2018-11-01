---
title: Hinzufügen von Versionsinformationen für eine andere Sprache (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version
helpviewer_keywords:
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
ms.assetid: 17f6273c-e1cc-441a-a3d8-f564341cbf20
ms.openlocfilehash: 6d79fb575817d5ba743e4efc460154eb03dca4f5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534588"
---
# <a name="adding-version-information-for-another-language-c"></a>Hinzufügen von Versionsinformationen für eine andere Sprache (C++)

### <a name="to-add-version-information-for-another-language-new-info-block"></a>So fügen Sie Versionsinformationen für eine andere Sprache hinzu (neuer Infoblock)

1. Öffnen Sie eine Versionsinformationsressource, indem Sie in der [Ressourcenansicht](../windows/resource-view-window.md)darauf doppelklicken.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Klicken Sie mit der rechten Maustaste in der Versionsinformationstabelle, und wählen Sie aus dem Kontextmenü **Neuer Versionsinformationsblock** aus.

   Dieser Befehl fügt der aktuellen Versionsinformationsressource einen zusätzlichen Informationsblock hinzu und öffnet dessen entsprechende Eigenschaften im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window).

3. Wählen Sie im **Eigenschaftenfenster** die Sprache und den Zeichensatz für den neuen Block aus.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Versionsinfo-Editor](../windows/version-information-editor.md)<br/>
[Versionsinformationen (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)