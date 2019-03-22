---
title: Binär-Editor (C++)
ms.date: 02/14/2019
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
ms.openlocfilehash: 0adcefe2af9d17a1c42f64f25636e220f53706fc
ms.sourcegitcommit: c1f646c8b72f330fa8cf5ddb0f8f261ba10d16f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2019
ms.locfileid: "58328752"
---
# <a name="binary-editor-c"></a>Binär-Editor (C++)

> [!CAUTION]
> Bearbeiten von Ressourcen wie z. B. Dialogfeldern, Bildern oder Menüs in die **Binär-Editor** ist riskant. Eine falsche Bearbeitung kann zu einer Beschädigung der Ressource führen, sodass sie anschließend im systemeigenen Editor nicht mehr einsetzbar ist.

Die **Binär-Editor** können Sie beliebige Ressourcen auf Binärebene im hexadezimalen Format oder im ASCII-Format bearbeiten. Außerdem können Sie mit dem [Suchbefehl](/visualstudio/ide/reference/find-command) ASCII-Zeichenfolgen oder hexadezimale Bytes suchen. Verwenden der **Binär-Editor** nur wenn Sie anzeigen oder geringfügige vornehmen müssen, benutzerdefinierte Ressourcen oder Ressourcentypen, die von Visual Studio-Umgebung nicht unterstützt wird geändert. Die **Binär-Editor** ist in Express-Editionen nicht verfügbar.

- Zum Öffnen der **Binär-Editor** auf eine neue Datei, wechseln Sie zum Menü **Datei** > **neu** > **Datei**, wählen Sie den Typ der Datei, die Sie bearbeiten möchten, und dann aktivieren Sie den Dropdownpfeil neben der **öffnen** , und wählen **Öffnen mit** > **Binär-Editor**.

- Zum Öffnen der **Binär-Editor** auf einer vorhandenen Datei, wechseln Sie zum Menü **Datei** > **öffnen** > **Datei**, wählen die Datei, die Sie bearbeiten möchten, und dann aktivieren Sie den Dropdownpfeil neben der **öffnen** , und wählen **Öffnen mit** > **Binär-Editor**.

   ![Binär-Editor](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")<br/>
   Binärdaten für ein Dialogfeld angezeigt, der **Binär-Editor**

Nur bestimmte ASCII-Werte dargestellt werden, der **Binär-Editor** (0 x 20 bis 0x7E). Erweiterte Zeichen werden als Punkte angezeigt, in im rechten Bereich ASCII-Wert-Abschnitt, der die **Binär-Editor**. Die druckbaren Zeichen sind ASCII-Werte 32 bis 126.

> [!TIP]
> Bei der Verwendung der **Binär-Editor**, können Sie in vielen Fällen mit der rechten Maustaste ein Kontextmenü mit ressourcenspezifische Befehle angezeigt. Welche Befehle verfügbar sind, hängt von dem Element ab, auf das Sie mit dem Cursor zeigen. Angenommen, Sie mit der rechten Maustaste beim Zeigen auf die die **Binär-Editor** mit Hexadezimalwerte markiert sind, zeigt das Kontextmenü der **Ausschneiden**, **Kopie**, und **Einfügen** Befehle.

## <a name="how-to"></a>Gewusst wie

Die **Binär-Editor** können Sie:

### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>So öffnen Sie eine Windows-Desktopressource zur Binärbearbeitung

1. Wählen Sie in der [Ressourcenansicht](how-to-create-a-resource-script-file.md#create-resources)die bestimmte Ressourcendatei aus, die Sie bearbeiten möchten.

1. Mit der rechten Maustaste in der Ressource, und wählen Sie **Binärdaten öffnen**.

> [!NOTE]
> Bei Verwendung der **Ressourcenansicht** Fenster aus, um eine Ressource in einem Format zu öffnen, die Visual Studio nicht erkannt werden, etwa eine RCDATA- oder eine benutzerdefinierte Ressource, die Ressource automatisch im geöffnet ist die **Binär-Editor**.

### <a name="to-open-a-managed-resource-for-binary-editing"></a>So öffnen Sie eine verwaltete Ressource für die Binärbearbeitung

1. In **Projektmappen-Explorer**, wählen Sie die bestimmte Ressourcendatei, die Sie bearbeiten möchten.

1. Mit der rechten Maustaste in der Ressource, und wählen Sie **Öffnen mit**.

1. Wählen Sie im Dialogfeld **Öffnen mit** den **Binär-Editor**aus.

> [!NOTE]
> Können Sie die [Bildbearbeitung](../windows/image-editor-for-icons.md) und **Binär-Editor** , Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

### <a name="to-edit-a-resource"></a>So bearbeiten Sie eine Ressource

Wenn Sie verwenden möchten. die **Binär-Editor** für eine Ressource, die bereits in einem anderen Editorfenster bearbeitet wird, zuerst das andere Editorfenster schließen.

1. Wählen Sie das Byte, die, das Sie bearbeiten möchten.

   Die **Registerkarte** Schlüssel verschiebt den Fokus zwischen der Hexadezimal- und ASCII-Teile der **Binär-Editor**. Können Sie die **Bild-auf** und **Seite nach unten** Schlüssel im einem Bildschirm "Resource" zu einem Zeitpunkt zu verschieben.

1. Geben Sie den neuen Wert ein.

   Der Wert Änderungen sofort in der sowohl Hexadezimal- und ASCII-Abschnitte und der Fokus wechselt zum nächsten Wert in Zeile.

> [!NOTE]
> Die **Binär-Editor** Änderungen automatisch akzeptiert, wenn Sie den Editor zu schließen.

### <a name="to-find-binary-data"></a>Binärdaten suchen

Sie können für ASCII-Zeichenfolgen oder hexadezimale Bytes suchen. Beispielsweise, um suchen *Hello*, Suche nach können Sie entweder die Zeichenfolge *Hello* oder seinem Hexadezimalwert, *48 65 6 c 6 C 6F*.

1. Wechseln Sie zum Menü **bearbeiten** > [finden](/visualstudio/ide/reference/find-command).

1. In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Daten, die Sie suchen möchten.

1. Aktivieren Sie keines der **finden** "Optionen", und wählen Sie **Weitersuchen**.

### <a name="to-create-a-new-custom-or-data-resource"></a>So erstellen Sie eine neue benutzerdefinierte oder Datenressource

Sie können eine neue benutzerdefinierte oder Datenressource erstellen, indem Sie die Ressource in einer separaten Datei mit der normalen Syntax von Ressourcenskriptdateien (RC), und klicken Sie dann die Datei einschließen, mit der rechten Maustaste in das Projekt im platzieren **Projektmappen-Explorer** und auswählen **Ressourcenincludes**.

1. [Erstellen Sie eine RC-Datei](../windows/how-to-create-a-resource-script-file.md) , die die benutzerdefinierte oder Datenressource enthält.

   Sie können benutzerdefinierte Daten in einer RC-Datei als in Anführungszeichen eingeschlossene nullterminierte Zeichenfolgen oder als ganze Zahlen im dezimalen, hexadezimalen oder oktalen Format eingeben.

1. In **Projektmappen-Explorer**mit der rechten Maustaste auf die RC-Datei des Projekts, und wählen Sie **Ressourcenincludes**.

1. In der **Kompilierzeitdirektiven** geben eine `#include` -Anweisung, die den Namen der Datei, die Ihre benutzerdefinierte Ressource, z. B. enthält enthält:

    ```cpp
    #include mydata.rc
    ```

   Achten Sie auf die korrekte Syntax und Rechtschreibung Ihrer Eingaben. Den Inhalt der **Kompilierzeitdirektiven** Feld genau wie die Eingabe in die Ressourcenskriptdatei eingefügt.

1. Wählen Sie **OK** um Ihre Änderungen aufzuzeichnen.

Eine weitere Möglichkeit zum Erstellen einer benutzerdefinierten Ressource ist eine externe Datei als benutzerdefinierte Ressource importieren, finden Sie unter [Vorgehensweise: Verwalten von Ressourcen](../windows/how-to-import-and-export-resources.md).

> [!NOTE]
> Erstellen neue benutzerdefinierte oder Ressourcen erfordert Win32.

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)