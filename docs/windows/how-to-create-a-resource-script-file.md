---
title: 'Vorgehensweise: Erstellen einer Ressourcenskriptdatei (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.editors.resource
helpviewer_keywords:
- rc files [C++], creating
- .rc files [C++], creating
- resource script files [C++], creating
- resources [C++], viewing
- rc files [C++], viewing resources
- .rc files [C++], viewing resources
- resource script files [C++], viewing resources
- resource script files [C++], opening in text format
- .rc files [C++], opening in text format
- rc files [C++], opening in text format
ms.assetid: 82be732a-cdcd-4a58-8de7-976d1418f86b
ms.openlocfilehash: f3f0adff256742c98a672e40e6b31de9bd7a84ed
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849957"
---
# <a name="how-to-create-a-resource-script-file-c"></a>Vorgehensweise: Erstellen einer Ressourcenskriptdatei (C++)

> [!NOTE]
> Die **Ressourcen-Editor-** ist in Express-Editionen nicht verfügbar.
>
> Diese Materialien beziehen sich auf Windows-Desktopanwendungen. Für Projekte in .NET-Sprachen werden keine Ressourcenskriptdateien verwendet. Weitere Informationen finden Sie unter [Ressourcendateien](../windows/resource-files-visual-studio.md), Weitere Informationen.

## <a name="to-create-a-new-resource-script-rc-file"></a>So erstellen Sie eine neue Ressourcenskriptdatei (RC-Datei)

1. Setzen Sie den Fokus auf den vorhandenen Projektordner in **Projektmappen-Explorer**, z. B. `MyProject`.

   > [!NOTE]
   > Verwechseln Sie nicht mit dem Projektmappenordner im Projektordner **Projektmappen-Explorer**. Wenn den Fokus verschieben, auf die **Lösung** -Ordner, Ihre Auswahl in der **neues Element hinzufügen** (Dialogfeld) (in Schritt 3) unterscheiden.

1. Wählen Sie im Menü **Projekt** die Option **Neues Element hinzufügen** aus.

1. In der **neues Element hinzufügen** wählen Sie im Dialogfeld die **Visual C++** Ordner wählen Sie dann **Ressourcendatei (.rc)** im rechten Bereich.

1. Geben Sie einen Namen für die Ressourcenskriptdatei in die **Namen** Text im Feld aus, und wählen Sie dann **öffnen**.

Sie können jetzt neue Ressourcen [erstellen](../windows/how-to-create-a-resource.md) und diese der RC-Datei hinzufügen.

> [!NOTE]
> Eine Ressourcenskriptdatei (.rc) kann nur in ein vorhandenes Projekt aufgenommen werden, das bereits in der Visual Studio-IDE geladen wurde. Es können keine eigenständige RC-Datei (außerhalb des Projekts) erstellt werden. [Ressourcenvorlagen](../windows/how-to-use-resource-templates.md) (RCT-Dateien) können jederzeit erstellt werden.

## <a name="to-open-a-resource-script-file-outside-of-a-c-project-standalone"></a>Zum Öffnen einer Ressourcenskriptdatei außerhalb eines C++-Projekts (eigenständig)

Sie können Ressourcen in einer RC-Datei anzeigen, ohne dass ein Projekt geöffnet sein muss. Die RC-Datei wird geöffnet, in einem Dokumentfenster geöffnet, anstatt in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster (wie dies der Fall ist, wenn die Datei innerhalb eines Projekts geöffnet ist).

> [!NOTE]
> Dies ist eine wichtige Unterscheidung, da einige Befehle nur verfügbar sind, wenn die Datei eigenständig (außerhalb eines Projekts) geöffnet wird. Beispielsweise Sie können nur eine Datei speichern in einem anderen Format oder als einen anderen Dateinamen an, wenn die Datei außerhalb eines Projekts geöffnet wird (die **speichern** Befehl ist nicht verfügbar, wenn eine Datei innerhalb eines Projekts geöffnet ist).

### <a name="to-open-an-rc-file-outside-a-project"></a>Öffnen einer RC-Datei außerhalb eines Projekts

1. Von der **Datei** Menü wählen **öffnen**, und wählen Sie dann **Datei**.

1. In der **geöffnete Datei** Dialogfeld navigieren Sie zur Ressourcenskriptdatei, die Sie anzeigen, markieren Sie die Datei, und wählen möchten **öffnen**.

   > [!NOTE]
   > Wenn Sie das Projekt zuerst öffnen (**Datei**, **öffnen**, **Projekt**), einige Befehle werden nicht zur Verfügung. Eine Datei „eigenständig“ zu öffnen, bedeutet, sie zu öffnen, ohne erst das Projekt zu laden.

### <a name="to-open-multiple-rc-files-outside-a-project"></a>Öffnen mehrerer RC-Dateien außerhalb eines Projekts

1. Öffnen Sie beide Ressourcendateien eigenständig. Öffnen Sie z. B. `Source1.rc` und `Source2.rc`.

   1. Von der **Datei** Menü wählen **öffnen**, und wählen Sie dann **Datei**.

   1. In der **Datei öffnen** Dialogfeld navigieren Sie zu den ersten Ressourcenskriptdatei, die Sie öffnen möchten (`Source1.rc`), markieren Sie die Datei, und wählen **öffnen**.

   1. Wiederholen Sie den vorherigen Schritt zum Öffnen der zweiten RC-Datei (`Source2.rc`).

       Die RC-Dateien sind nun in separaten Dokumentfenstern geöffnet.

1. Wenn beide RC-Dateien geöffnet sind, ordnen Sie die Fenster so an, dass sie gleichzeitig angezeigt werden:

   - Von der **Fenster** Menü wählen **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe**.

       \- oder –

   - Mit der rechten Maustaste eine der RC-Dateien, und wählen Sie **neue horizontale Registerkartengruppe** oder **neue vertikale Registerkartengruppe** aus dem Kontextmenü.

> [!NOTE]
> Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

## <a name="to-open-a-resource-script-file-in-text-format"></a>Zum Öffnen einer Ressourcenskriptdatei im Textformat

Es gibt viele Situationen, in denen Sie die Inhalte der Ressourcenskriptdatei (.rc) Ihres Projekts anzeigen möchten, ohne dafür eine Ressource wie ein Dialogfeld im entsprechenden Ressourcen-Editor zu öffnen. Beispielsweise möchten Sie möglicherweise nach einer Zeichenfolge über alle Dialogfelder in der Ressourcendatei hinweg suchen, ohne dass Sie dafür jedes einzeln öffnen müssen.

> [!NOTE]
> Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

Sie können die Ressourcendatei einfach öffnen, im Text-Format, um alle darin enthaltenen Ressourcen anzuzeigen, und führen globale Vorgänge, die von den Text-Editor unterstützt werden.

> [!NOTE]
> Die Ressourcen-Editoren nicht direkt RC gelesen oder `resource.h` Dateien. Der Ressourcencompiler kompiliert sie in .aps-Dateien, die von den Ressourcen-Editoren genutzt werden. Diese Datei ist ein Kompilierungsschritt und speichert nur symbolische Daten. Wie bei einer normalen Kompilierung werden Informationen, die nicht symbolisch sind (z. B. Kommentare) während der Kompilierung verworfen. Sobald die .aps-Datei nicht mehr mit der .rc-Datei synchron ist, wird die .rc-Datei neu generiert (z. B. überschreibt der Ressourcen-Editor beim Speichern die .rc-Datei und resource.h-Datei). Alle Änderungen an den Ressourcen selbst bleiben in der .rc-Datei, aber Kommentare gehen immer verloren, sobald die .rc-Datei überschrieben wird. Weitere Informationen zur Erhaltung von Kommentaren, finden Sie unter [Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md).

### <a name="to-open-a-resource-script-file-as-text"></a>So öffnen Sie eine Ressourcenskriptdatei als Text

1. Von der **Datei** Menü **öffnen**, wählen Sie dann **Datei**.

1. In der **geöffnete Datei** Dialogfeld navigieren Sie auf die Ressourcenskriptdatei im Textformat anzeigen möchten.

1. Markieren Sie die Datei, und wählen Sie auf den Dropdown-Pfeil der **öffnen** Schaltfläche (auf der rechten Seite der Schaltfläche).

1. Wählen Sie **Öffnen mit** im Dropdown-Menü.

1. In der **Öffnen mit** wählen Sie im Dialogfeld **Quellcode-Editor (Text)**.

1. Von der **öffnen als** Dropdown-Liste **Text**.

   Die Ressource wird geöffnet, der **Quellcode** Editor.

\- oder –

1. In **Projektmappen-Explorer**, mit der rechten Maustaste in der RC-Datei.

1. Wählen Sie im Kontextmenü den Befehl **Öffnen mit...** , und wählen Sie dann **Quellcode-Editor (Text)**.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)