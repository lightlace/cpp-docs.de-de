---
title: 'Vorgehensweise: Verwenden von Ressourcenvorlagen (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- language-specific template files [C++]
- resource templates
- resources [C++], creating
- rct files [C++]
- templates, resource templates
- resources [C++], templates
- .rct files [C++]
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
ms.openlocfilehash: d92579214dec96ea67537b4eb37e4554054d411d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577384"
---
# <a name="how-to-use-resource-templates-c"></a>Vorgehensweise: Verwenden von Ressourcenvorlagen (C++)

Eine Ressourcenvorlage ist eine benutzerdefinierte Ressource, die Sie als RCT-Datei gespeichert haben. Eine Ressourcenvorlage kann dann als Ausgangspunkt für die Erstellung weiterer Ressourcen dienen. Ressourcenvorlagen sparen Zeit bei der Entwicklung von zusätzlichen Ressourcen oder Gruppen von Ressourcen, die Funktionen wie Standardsteuerelemente oder andere wiederkehrende Elemente gemeinsam nutzen. Zum Beispiel können Sie eine Hilfeschaltfläche und ein Symbol eines Firmenlogos in mehrere Dialogfelder einfügen. Um dies schnell zu tun, erstellen Sie eine neue Dialogfeldvorlage, und passen Sie sie mit dem Logo und der Hilfeschaltfläche an.

Nachdem Sie die Ressourcenvorlage angepasst haben, müssen Sie die Änderungen im Vorlagenordner (oder einem beliebigen Speicherort im Includepfad angegeben) speichern, damit die neue Ressourcenvorlage unter ihrem Ressourcentyp im angezeigt werden, wird die [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md). Sie können die neue Ressourcenvorlage dann beliebig oft verwenden.

> [!NOTE]
> Sie können sprachspezifische Vorlagendateien in Unterverzeichnissen des zentralen Vorlagenverzeichnisses platzieren. Sie können z. B. nur Englisch-Vorlagendateien im platzieren \\< ressourcenvorlagenverzeichnis\>\1033.

### <a name="to-create-a-template-for-resources"></a>So erstellen Sie eine Vorlage für Ressourcen

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in Ihrem Projekts.

2. Wählen Sie im Kontextmenü den Befehl **hinzufügen**, klicken Sie dann auf **neues Element hinzufügen**.

3. In der **neues Element hinzufügen** Dialogfeld die **Vorlagen:** Bereich wählen **Ressourcenvorlagendatei (.rct)**.

4. Geben Sie einen Namen und Speicherort für die neue RCT-Datei, und klicken Sie auf **öffnen**.

5. Die neue RCT-Datei wird dem Projekt hinzugefügt und wird im **Projektmappen-Explorer** unter der **Ressourcen** Ordner.

   Sie können jetzt Doppelklicken Sie auf die RCT-Datei, um sie in einem Dokumentfenster zu öffnen, und klicken Sie dann Ressourcen hinzufügen (mit der rechten Maustaste in der Datei im Dokumentfenster, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü). Dann können Sie diese Ressourcen anpassen und die RCT-Datei speichern.

   > [!NOTE]
   > Wenn Sie eine neue RCT-Datei erstellen, Visual Studio wird diese unter \Programme\Microsoft Visual Studio 9.0\VC\VCResourceTemplates unter \Programme\Microsoft Visual Studio 9.0\VC\VCResourceTemplates\\*LCID* () z. B. 1033 für Englisch) *oder* überall auf der [Includepfad](../windows/how-to-specify-include-directories-for-resources.md). Wenn Sie es vorziehen, die RCT-Dateien in einem anderen Dateiordner zu speichern, z. B. \Eigene Dokumente, müssen Sie diesen Ordner lediglich zum Includepfad hinzufügen und Visual Studio findet die RCT-Datei.

### <a name="to-convert-an-existing-rc-file-to-an-rct-file"></a>So konvertieren Sie eine vorhandene RC-Datei in eine RCT-Datei

1. [Öffnen Sie die RC-Datei als eigenständige Datei](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

2. Auf der **Datei** Menü klicken Sie auf **speichern \< *Dateiname*> als**.

3. Geben Sie einen Speicherort aus, und klicken Sie auf **OK**.

### <a name="to-create-a-new-resource-from-a-template"></a>So erstellen Sie eine neue Ressource aus einer Vorlage

1. In der [Ressourcenansicht](../windows/resource-view-window.md) Bereich, klicken Sie mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.

2. In der **Ressource hinzufügen** Dialogfeld klicken Sie auf das Pluszeichen (**+**) neben einer Ressource, um den Ressourcenknoten zu erweitern und alle für diese Ressource verfügbaren Vorlagen anzuzeigen.

3. Doppelklicken Sie auf die Vorlage, die Sie verwenden möchten.

4. Ändern Sie die hinzugefügte Ressource nach Bedarf im zugehörigen Ressourcen-Editor.

   Der Ressourcen-Editor stellt automatisch eine eindeutige Ressourcen-ID bereit. Sie können Überarbeiten der [Ressourceneigenschaften](../windows/changing-the-properties-of-a-resource.md) je nach Bedarf.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)