---
title: 'Vorgehensweise: Erstellen Sie eine Ressource (C++)'
ms.date: 11/04/2016
f1_keywords:
- vs.resourceview.F1
- vc.editors.insertresource
- vc.editors.newcustomresource
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
- resources [C++], viewing
- Resource View window
- resources [C++], adding
- Add Resource dialog box [C++]
- Custom Resource Type dialog box [C++]
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
ms.openlocfilehash: fdf158bab7894497dbcfb147eb2c6e061879be75
ms.sourcegitcommit: 63c072f5e941989636f5a2b13800b68bb7129931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2019
ms.locfileid: "55764050"
---
# <a name="how-to-create-a-resource-c"></a>Vorgehensweise: Erstellen Sie eine Ressource (C++)

Die **Ressourcenansicht** Fenster werden die im Projekt enthaltenen Ressourcendateien angezeigt. Bei Erweitern des obersten Ordners (z. B. Projekt1.rc) werden die Ressourcentypen aus dieser RC-Datei angezeigt. Beim Erweitern der einzelnen Ressourcentypen werden die einzelnen Ressourcen dieses Typs angezeigt.

> [!NOTE]
> Diese Informationen gelten nicht für Ressourcen in den apps der universellen Windows-Plattform. Weitere Informationen finden Sie unter [App-Ressourcen und das Ressourcenverwaltungssystem](/windows/uwp/app-resources/).

> [!NOTE]
> **Ressourcenansicht** wird in Express-Editionen nicht unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*.

> [!NOTE]
> Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

Die **Ressourcenansicht** Fenster verwendet die **Ressource hinzufügen** Ressourcen zu einem C++-Windows-desktop-Anwendung-Projekt hinzufügen. Dieses Dialogfeld enthält die folgenden Eigenschaften:

|Eigenschaft|Beschreibung|
|---|---|
|**Ressourcentyp**|Gibt die Art der zu erstellenden Ressource an.<br/><br/>Der Cursor und die Kategorien der Dialogfeldressourcen können zum Anzeigen zusätzlicher Ressourcen erweitert werden. Diese Ressourcen befinden sich im Visual Studio-...\Microsoft `version`\VC\VCResourceTemplates\\< LCID\>\mfc.rct. Wenn Sie RCT-Dateien hinzufügen, Sie sie in diesem Verzeichnis ablegen müssen oder Sie angeben müssen, ein [Includepfad](../windows/how-to-specify-include-directories-for-resources.md) für sie. Die Ressourcen in diesen Dateien werden dann auf der zweiten Ebene der entsprechenden Kategorie angezeigt. Es ist nicht beschränkt auf die Anzahl von RCT-Dateien, die Sie hinzufügen können.<br/><br/>Die auf der obersten Ebene der Strukturansicht angezeigten Ressourcen sind die von Visual Studio bereitgestellten Standardressourcen.|
|**Neu**|Erstellt eine Ressource anhand des Typs, die Sie, in ausgewählt haben der **Ressourcentyp** Feld. Die Ressource wird im geeigneten Editor geöffnet. Beispielsweise wenn Sie eine Ressource erstellen, es öffnet der [Dialog-Editor](../windows/dialog-editor.md).|
|**Importieren**|Öffnet die **importieren** Dialogfeld, in dem gelangen Sie zu einer Ressource Sie, möchten in Ihrem aktuellen Projekt zu importieren. Sie können eine Bitmap, ein Symbol, einen Cursor, eine HTML-Ressourcendatei, eine Sound-Ressourcendatei (.WAV) oder eine benutzerdefinierte Ressourcendatei importieren.|
|**Benutzerdefiniert**|Öffnet die **neue benutzerdefinierte Ressource** Dialogfeld, in dem Sie eine benutzerdefinierte Ressource erstellen können. Benutzerdefinierte Ressourcen können nur im Binär-Editor bearbeitet werden.|

Die **neue benutzerdefinierte Ressource** Dialogfeld können Sie eine neue benutzerdefinierte Ressource in einem C++-Projekt zu erstellen. Dieses Dialogfeld enthält die folgende Eigenschaft:

|Eigenschaft|Beschreibung|
|---|---|
|**Ressourcentyp**|Stellt ein Textfeld zur Eingabe der Name eines benutzerdefinierten Ressourcentyps bereit. Visual C++ nutzt den Namen automatisch beim Beenden der **neue benutzerdefinierte Ressource** Dialogfeld.|

Wenn Sie eine neue Ressource erstellen, Visual C++ weist einen eindeutigen Namen, z. B. `IDD_Dialog1`. Sie können diese Ressourcen-ID anpassen, indem Sie die Ressourceneigenschaften entweder im zugehörigen Ressourcen-Editor oder im [Eigenschaftenfenster](/visualstudio/ide/reference/properties-window)bearbeiten.

Sie können eine Ressource erstellen, als neue Standardressource (eine Ressource, die nicht in einer Vorlage basiert) oder als eine Ressource, die dem Muster einer [Vorlage](../windows/how-to-use-resource-templates.md).

> [!NOTE]
> Geben Sie kein Ressourcenname oder ID, die von Visual Studio reserviert ist. Die reservierten Namen lauten DESIGNINFO, HWB und TEXTINCLUDE, die reservierte ID lautet 255.

## <a name="to-open-the-resource-view-window"></a>So öffnen Sie das Fenster "Ressourcenansicht"

Wählen Sie **Ressourcenansicht** auf die **Ansicht** Menü.

   \- oder –

Drücken Sie **STRG** + **UMSCHALT** + **E**.

> [!TIP]
> Sie können mit der rechten Maustaste auf die **Ressourcenansicht** Fenster aus, um ein Kontextmenü mit Befehlen zu starten. Außerdem kann das Fenster mit einem Doppelklick auf die Titelleiste verankert bzw. die Verankerung gelöst werden. Durch Klicken mit der rechten Maustaste auf die Titelleiste werden zusätzliche Befehle zum Steuern des Fensterverhaltens angezeigt. Weitere Informationen finden Sie unter [Windows Management](/visualstudio/ide/customizing-window-layouts-in-visual-studio).

## <a name="to-create-a-new-resource-in-resource-view"></a>So erstellen Sie eine neue Ressource in der Ressourcenansicht

1. Mit dem Schwerpunkt auf die RC-Datei in **Ressourcenansicht**, wählen die **bearbeiten** Menü, und wählen Sie **Ressource hinzufügen** (oder mit der rechten Maustaste in der RC-Datei **Ressourcenansicht** , und wählen Sie **Ressource hinzufügen** aus dem Kontextmenü).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. In der **Ressource hinzufügen** Dialogfeld Wählen Sie den Typ der Ressource, die Sie Ihrem Projekt hinzufügen möchten.

## <a name="to-create-a-new-resource-in-solution-explorer"></a>So erstellen Sie eine neue Ressource im Projektmappen-Explorer

1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektordner, und wählen Sie **Hinzufügen**aus. Klicken Sie dann im Kontextmenü auf **Ressource hinzufügen** .

   Wenn Sie noch keine RC-Datei in Ihrem Projekt haben, wird in diesem Schritt eine erstellt. Anschließend können Sie diesen Schritt wiederholen, um der neuen RC-Datei spezifische Ressourcentypen hinzuzufügen.

2. In der **Ressource hinzufügen** Dialogfeld Wählen Sie den Typ der Ressource, die Sie Ihrem Projekt hinzufügen möchten.

## <a name="to-create-a-new-resource-in-class-view"></a>So erstellen Sie eine neue Ressource in der Klassenansicht

1. In [Klassenansicht](/visualstudio/ide/viewing-the-structure-of-code)mit der rechten Maustaste auf die Klasse, und wählen Sie **hinzufügen**, und wählen Sie dann **Ressource hinzufügen** aus dem Kontextmenü.

2. In der **Ressource hinzufügen** Dialogfeld Wählen Sie den Typ der Ressource, die Sie Ihrem Projekt hinzufügen möchten.

## <a name="to-create-a-new-resource-from-the-project-menu"></a>So erstellen Sie eine neue Ressource über das Menü "Projekt"

Wählen Sie im Menü **Projekt** den Befehl **Ressource hinzufügen**aus.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Arbeiten mit Ressourcendateien](../windows/working-with-resource-files.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
