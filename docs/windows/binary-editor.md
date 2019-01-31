---
title: Binär-Editor (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.binary.F1
- vc.editors.binary
helpviewer_keywords:
- editors, Binary
- resources [C++], editing
- resource editors [C++], Binary editor
- Binary editor
- binary data, editing
- resources [C++], opening for binary editing
- binary data
- hexadecimal bytes in binary data
- strings [C++], searching for
- file searches [C++]
- binary data, finding
- ASCII characters, finding in binary data
- custom resources [C++]
- data resources [C++]
- resources [C++], creating
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
ms.openlocfilehash: 06c4a224b745f5aba8c9105d32489f8ca3109e1c
ms.sourcegitcommit: b488462a6e035131121e6f32d8f3b108cc798b5e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55293597"
---
# <a name="binary-editor-c"></a>Binär-Editor (C++)

> [!WARNING]
> Die **Binär-Editor** ist in Express-Editionen nicht verfügbar.

Der Binär-Editor ermöglicht eine Bearbeitung beliebige Ressourcen auf Binärebene im hexadezimalen Format oder im ASCII-Format. Außerdem können Sie mit dem [Suchbefehl](/visualstudio/ide/reference/find-command) ASCII-Zeichenfolgen oder hexadezimale Bytes suchen. Verwenden Sie die **binäre** Editor lediglich bei Bedarf anzeigen oder geringfügige Änderungen, benutzerdefinierte Ressourcen oder Ressourcentypen, die von Visual Studio-Umgebung nicht unterstützt.

Zum Öffnen der **Binär-Editor**, wählen Sie zuerst **Datei** > **neu** > **Datei** wählen Sie im Hauptmenü auf der Datei, die Sie bearbeiten möchten, und dann klicken auf den Dropdownpfeil neben der **öffnen** , und wählen **Öffnen mit** > **Binär-Editor**.

> [!CAUTION]
> Das Bearbeiten von Ressourcen, wie Dialogfeldern, Bildern oder Menüs ist im Binär-Editor äußerst riskant. Eine falsche Bearbeitung kann zu einer Beschädigung der Ressource führen, sodass sie anschließend im systemeigenen Editor nicht mehr einsetzbar ist.

> [!TIP]
> Bei der Verwendung der **binäre** -Editor, in vielen Fällen, Sie können mit der rechten Maustaste ein Kontextmenü mit ressourcenspezifische Befehle angezeigt. Welche Befehle verfügbar sind, hängt von dem Element ab, auf das Sie mit dem Cursor zeigen. Angenommen, Sie klicken können, während Sie auf die **binäre** -Editor mit Hexadezimalwerte markiert sind, im Kontextmenü werden die **Ausschneiden**, **Kopie**, und **einfügen**  Befehle.

## <a name="binary-editor-how-to"></a>Exemplarische Vorgehensweise die Binär-Editor

Mit der **binäre** -Editor finden Sie unter der folgenden Aktionen:

### <a name="to-open-a-resource-for-binary-editing"></a>Um eine Ressource für die binärbearbeitung öffnen

#### <a name="to-open-a-windows-desktop-resource"></a>Um eine Windows-desktop-Ressource zu öffnen.

1. Wählen Sie in der [Ressourcenansicht](../windows/resource-view-window.md)die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

1. Klicken Sie mit der rechten Maustaste auf die Ressource, und klicken Sie im Kontextmenü auf **Binärdaten öffnen** .

   > [!NOTE]
   > Bei Verwendung der [Ressourcenansicht](../windows/resource-view-window.md) Fenster aus, um eine Ressource in einem Format zu öffnen, dass Visual Studio nicht (etwa eine RCDATA- oder eine benutzerdefinierte Ressource), die Ressource erkennt wird automatisch geöffnet, der **binäre** Editor.

#### <a name="to-open-a-managed-resource"></a>Um eine verwaltete Ressource zu öffnen.

1. In **Projektmappen-Explorer**, wählen Sie die bestimmte Ressourcendatei, die Sie bearbeiten möchten.

1. Klicken Sie mit der rechten Maustaste auf die Ressource, und wählen Sie im Kontextmenü **Öffnen mit** aus.

1. Wählen Sie im Dialogfeld **Öffnen mit** den **Binär-Editor**aus.

   > [!NOTE]
   > Mit der [Bildbearbeitung](../windows/image-editor-for-icons.md) und dem [Binär-Editor](binary-editor.md) ist die Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

![Binär-Editor](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
Binärdaten für ein Dialogfeld in der Darstellung im Binär-Editor

Nur bestimmte ASCII-Werte werden im Binär-Editor dargestellt (0x20 bis 0x7E). Erweiterte Zeichen werden im Bereich „ASCII-Wert“ des Binär-Editors (dem rechten Bereich) als Punkte dargestellt. Die "druckbaren" Zeichen sind die ASCII-Werte 32 bis 126.

> [!NOTE]
> Wenn Sie verwenden möchten. die **binäre** -Editor auf eine Ressource, die bereits in einem anderen Editorfenster bearbeitet wird schließen Sie zuerst das andere Editorfenster.

### <a name="to-edit-a-resource-in-the-binary-editor"></a>So bearbeiten Sie eine Ressource im Binär-editor

1. Wählen Sie das Byte, die, das Sie bearbeiten möchten.

   Die **Registerkarte** Schlüssel verschiebt den Fokus zwischen der Hexadezimal- und ASCII-Teile der **binäre** Editor. Können Sie die **Bild-auf** und **Seite nach unten** Schlüssel im einem Bildschirm "Resource" zu einem Zeitpunkt zu verschieben.

1. Geben Sie den neuen Wert ein.

   Der Wert Änderungen sofort in der sowohl Hexadezimal- und ASCII-Abschnitte und der Fokus wechselt zum nächsten Wert in Zeile.

   > [!NOTE]
   > Die **binäre** Editor nimmt Änderungen automatisch, wenn Sie den Editor zu schließen.

### <a name="to-find-binary-data"></a>Binärdaten suchen

Sie können für ASCII-Zeichenfolgen oder hexadezimale Bytes suchen. Z. B. um "Hello" zu suchen, Sie können entweder die Zeichenfolge "Hello" oder suchen für "48 65 6 c 6 C 6F" (die hexadezimale Entsprechung).

1. Von der **bearbeiten** Menü wählen [finden](/visualstudio/ide/reference/find-command).

1. In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Daten, die Sie suchen möchten.

1. Aktivieren Sie keines der **finden** Optionen.

1. Wählen Sie **Weitersuchen**.

### <a name="to-create-a-new-custom-or-data-resource"></a>So erstellen Sie eine neue benutzerdefinierte oder Datenressource

Sie können eine neue benutzerdefinierte oder Datenressource erstellen, indem Sie die Ressource in einer separaten Datei mit der normalen Syntax von Ressourcenskriptdateien (RC), und klicken Sie dann die Datei einschließen, mit der rechten Maustaste in das Projekt im platzieren **Projektmappen-Explorer** und auf **Ressource umfasst** im Kontextmenü auf.

1. [Erstellen Sie eine RC-Datei](../windows/how-to-create-a-resource-script-file.md) , die die benutzerdefinierte oder Datenressource enthält.

   Sie können benutzerdefinierte Daten in einer RC-Datei als in Anführungszeichen eingeschlossene nullterminierte Zeichenfolgen oder als ganze Zahlen im dezimalen, hexadezimalen oder oktalen Format eingeben.

1. Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf die RC-Datei Ihres Projekts, und klicken Sie dann im Kontextmenü auf **Ressourcenincludes** .

1. In der **Kompilierzeitdirektiven** geben eine `#include` -Anweisung, die den Namen der Datei mit der benutzerdefinierten Ressource enthält. Zum Beispiel:

    ```cpp
    #include mydata.rc
    ```

   Achten Sie auf die korrekte Syntax und Rechtschreibung Ihrer Eingaben. Der Inhalt des Felds **Kompilierzeitdirektiven** wird in die Ressourcenskriptdatei genau so eingefügt, wie sie ihn eingegeben haben.

1. Wählen Sie **OK** um Ihre Änderungen aufzuzeichnen.

Eine weitere Möglichkeit zum Erstellen einer benutzerdefinierten Ressource ist das Importieren einer externen Datei als benutzerdefinierte Ressource. Weitere Informationen finden Sie unter [Importieren und Exportieren von Ressourcen](../windows/how-to-import-and-export-resources.md).

> [!NOTE]
> Erstellen neue benutzerdefinierte oder Ressourcen erfordert Win32.

## <a name="managed-resources"></a>Verwaltete Ressourcen

Können Sie die [bildbearbeitung](../windows/image-editor-for-icons.md) und **binäre** -Editor, um die Arbeit mit Ressourcendateien in verwalteten Projekten. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keine

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)