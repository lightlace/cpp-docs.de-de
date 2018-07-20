---
title: 'Vorgehensweise: Verwenden von Ressourcenvorlagen | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- language-specific template files
- resource templates
- resources [Visual Studio], creating
- rct files
- templates, resource templates
- resources [Visual Studio], templates
- .rct files
ms.assetid: bdfe7060-f98e-4859-8285-9c8570360e9d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 534a86d10a4bcbc34e6cef29fbb77d7caa2c64b9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33882731"
---
# <a name="how-to-use-resource-templates"></a>Gewusst wie: Verwenden von Ressourcenvorlagen
Eine Ressourcenvorlage ist eine benutzerdefinierte Ressource, die Sie als RCT-Datei gespeichert haben. Eine Ressourcenvorlage kann dann als Ausgangspunkt für die Erstellung weiterer Ressourcen dienen. Ressourcenvorlagen sparen Zeit bei der Entwicklung von zusätzlichen Ressourcen oder Gruppen von Ressourcen, die Funktionen wie Standardsteuerelemente oder andere wiederkehrende Elemente gemeinsam nutzen. Zum Beispiel können Sie eine Hilfeschaltfläche und ein Symbol eines Firmenlogos in mehrere Dialogfelder einfügen. Um dies schnell zu tun, erstellen Sie eine neue Dialogfeldvorlage, und passen Sie sie mit dem Logo und der Hilfeschaltfläche an.  
  
 Nachdem Sie die Ressourcenvorlage angepasst haben, müssen Sie die Änderungen im Vorlagenordner (oder einem anderen im Includepfad angegebenen Speicherort) speichern, damit die neue Ressourcenvorlage unter ihrem Ressourcentyp im erscheint die [Dialogfeld "Ressource hinzufügen"](../windows/add-resource-dialog-box.md). Sie können die neue Ressourcenvorlage dann beliebig oft verwenden.  
  
> [!NOTE]
>  Sie können sprachspezifische Vorlagendateien in Unterverzeichnissen des zentralen Vorlagenverzeichnisses platzieren. Sie können z. B. nur die englische Vorlagendateien in platzieren \\< ressourcenvorlagenverzeichnis\>\1033.  
  
### <a name="to-create-a-template-for-resources"></a>So erstellen Sie eine Vorlage für Ressourcen  
  
1.  In **Projektmappen-Explorer**, mit der rechten Maustaste des Projekts.  
  
2.  Wählen Sie im Kontextmenü **hinzufügen**, klicken Sie dann auf **neues Element hinzufügen**.  
  
3.  In der **neues Element hinzufügen** Dialogfeld die **Vorlagen:** Bereich auswählen **Ressourcenvorlagendatei (.rct)**.  
  
4.  Geben Sie einen Namen und Speicherort für die neue RCT-Datei, und klicken Sie auf **öffnen**.  
  
5.  Die neue RCT-Datei wird dem Projekt hinzugefügt und wird im Projektmappen-Explorer unter dem **Ressourcen** Ordner.  
  
     Können Sie jetzt Doppelklicken Sie auf die RCT-Datei, um sie in einem Dokumentfenster zu öffnen und dann Ressourcen hinzufügen (mit der rechten Maustaste in der Datei im Dokumentfenster angezeigt, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü). Dann können Sie diese Ressourcen anpassen und die RCT-Datei speichern.  
  
    > [!NOTE]
    >  Wenn Sie eine neue RCT-Datei erstellen, Visual Studio sucht unter \Programme\Microsoft Visual Studio 9.0\VC\VCResourceTemplates unter \Programme\Microsoft Visual Studio 9.0\VC\VCResourceTemplates\\*LCID* () z. B. 1033 für Englisch) *oder* an einer beliebigen Stelle auf der [Includepfad](../windows/how-to-specify-include-directories-for-resources.md). Wenn Sie es vorziehen, die RCT-Dateien in einem anderen Dateiordner zu speichern, z. B. \Eigene Dokumente, müssen Sie diesen Ordner lediglich zum Includepfad hinzufügen und Visual Studio findet die RCT-Datei.  
  
### <a name="to-convert-an-existing-rc-file-to-an-rct-file"></a>So konvertieren Sie eine vorhandene RC-Datei in eine RCT-Datei  
  
1.  [Öffnen Sie die RC-Datei als eigenständige Datei](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).  
  
2.  Auf der **Datei** Menü klicken Sie auf **speichern \< *Dateiname*> als**.  
  
3.  Geben Sie einen Speicherort aus, und klicken Sie auf **OK**.  
  
### <a name="to-create-a-new-resource-from-a-template"></a>So erstellen Sie eine neue Ressource aus einer Vorlage  
  
1.  In der [Ressourcenansicht](../windows/resource-view-window.md) Bereich, klicken Sie mit der mit der rechten Maustaste auf die RC-Datei, und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü.  
  
2.  In der **Ressource hinzufügen** Dialogfeld klicken Sie auf das Pluszeichen (**+**) neben einer Ressource, um den Ressourcenknoten zu erweitern und alle für diese Ressource verfügbaren Vorlagen anzuzeigen.  
  
3.  Doppelklicken Sie auf die Vorlage, die Sie verwenden möchten.  
  
4.  Ändern Sie die hinzugefügte Ressource nach Bedarf im zugehörigen Ressourcen-Editor.  
  
     Der Ressourcen-Editor stellt automatisch eine eindeutige Ressourcen-ID bereit. Sie können ändern, die [Ressourceneigenschaften](../windows/changing-the-properties-of-a-resource.md) nach Bedarf.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.*  
  
 Anforderungen  
  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Ressourcendateien](../windows/resource-files-visual-studio.md)   
 [Ressourcen-Editor](../windows/resource-editors.md)