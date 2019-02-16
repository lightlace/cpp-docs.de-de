---
title: 'Vorgehensweise: Verwalten von Ressourcen (C++)'
ms.date: 02/14/2019
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
- vb.xmldesigner.data
- vs.resvw.resource.importing
- vc.resvw.resource.importing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
- .resx files [C++], editing
- resource files [C++], editing
- resx files [C++], editing
- resources [C++], exporting
- graphics [C++], exporting
- graphics [C++], importing
- resources [C++], importing
- bitmaps [C++], importing and exporting
- toolbars [C++], importing
- images [C++], importing
- toolbars [C++], exporting
- cursors [C++], importing and exporting
- images [C++], exporting
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 1f176b3fa19374b402039ecca60e690ade5c0cef
ms.sourcegitcommit: 470de1337035dd33682d935b4b6c6d8b1bdb0bbb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2019
ms.locfileid: "56320626"
---
# <a name="how-to-manage-resources-c"></a>Vorgehensweise: Verwalten von Ressourcen (C++)

## <a name="copy-resources"></a>Kopieren von Ressourcen

Sie können Ressourcen in eine andere aus einer Datei kopieren, ohne sie zu ändern, oder Sie können die Sprache oder Bedingung einer Ressource während des Kopiervorgangs ändern.

Sie können Ressourcen problemlos aus einer vorhandenen Ressource oder die ausführbare Datei in Ihre aktuelle Ressourcendatei kopieren. Um Ressourcen zu kopieren, öffnen Sie beide Dateien, die mit Ressourcen zur gleichen Zeit Sie und ziehen Sie Elemente aus einer Datei in eine andere oder kopieren und fügen Sie zwischen den beiden Dateien. Diese Methode funktioniert für Ressourcenskriptdateien (RC) und Ressourcendateien für die Vorlage (.rct) sowie als ausführbare Dateien (.exe).

> [!NOTE]
> Visual C++ enthält Beispiel-Ressourcendateien, die Sie in Ihrer eigenen Anwendung verwenden können. Weitere Informationen finden Sie unter [CLIPART: Allgemeine Ressourcen](https://github.com/Microsoft/VCSamples).

Sie können die Drag & Drop-Methode verwenden, RC-Dateien, die geöffnet sind [außerhalb des Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

### <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>So kopieren Sie Ressourcen zwischen den Dateien, die mithilfe der Drag & Drop-Methode

1. Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen in einer RC-Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Öffnen Sie z. B. *Source1.rc* und *Source2.rc*.

1. Wählen Sie in der ersten RC-Datei die Ressource, die Sie kopieren möchten. Z. B. in *Source1.rc*Option **IDD_DIALOG1**.

1. Halten Sie die **STRG** gedrückt, und ziehen Sie die Ressource in der zweiten RC-Datei. Ziehen Sie z. B. **IDD_DIALOG1** aus *Source1.rc* zu *Source2.rc*.

   > [!NOTE]
   > Ziehen die Ressource ohne gedrückt der **STRG** drücken, das verschoben wird, die Ressource, statt es zu kopieren.

### <a name="to-copy-resources-using-copy-and-paste"></a>Zum Kopieren von Ressourcen mithilfe von kopieren und einfügen

1. Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen in einer RC-Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Z. B. *Source1.rc* und *Source2.rc*.

1. In der Quelldatei, die von dem Sie eine Ressource zu kopieren möchten (z. B. *Source1.rc*) mit der rechten Maustaste auf eine Ressource, und wählen Sie **Kopie** aus dem Kontextmenü.

1. Mit der rechten Maustaste in der Ressourcendatei in die Sie die Ressource einfügen möchten (z. B. *Source2.rc*). Wählen Sie **einfügen** aus dem Kontextmenü.

   > [!NOTE]
   > Sie können keine drag und drop, kopieren, Ausschneiden, oder fügen Sie zwischen Ressourcendateien im Projekt (**Ressourcenansicht**) und eigenständige RC-Dateien (die im Dokumentfenster geöffnet). In früheren Versionen des Produkts können Sie dazu.

   > [!NOTE]
   > Um Konflikte mit Symbolnamen oder Werten in die vorhandene Datei zu vermeiden, kann Visual C++ Symbolwert der übertragenen Ressource oder Symbolnamens und-Werts ändern, wenn Sie ihn in die neue Datei kopieren.

### <a name="change-the-language-or-condition-of-a-resource-while-copying"></a>Ändern der Sprache oder Bedingung einer Ressource während des Kopierens

Beim Kopieren in eine Ressource können Sie ihre Sprachen- und/oder Bedingungseigenschaft ändern.

- Die Ressourcensprache ermittelt lediglich die Sprache für die Ressource. Die Sprache wird verwendet, indem [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) können Sie die Ressource zu identifizieren, für die Sie suchen. (Allerdings Ressourcen können Unterschiede für jede Sprache, die nicht mit Text verknüpft sind, erstellt z. B. Tastenkombinationen, die möglicherweise nur auf einer japanischen Tastatur funktionieren oder eine Bitmap, die nur für Chinesisch gilt geeignet wären.)

- Die Bedingung einer Ressource stellt ein definiertes Symbol dar, das eine Bedingung angibt, unter der diese bestimmte Ressourcenkopie zu verwenden ist.

Die Sprache und Bedingung einer Ressource in Klammern angezeigt, nach dem Namen der Ressource in der **Arbeitsbereich** Fenster. In diesem Beispiel ist die Ressource mit dem Namen `IDD_AboutBox` verwendet `Finnish` ist als seine Sprache und der Bedingung `XX33`.

```cpp
IDD_AboutBox (Finnish - XX33)
```

#### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>So kopieren Sie eine vorhandene Ressource und ändern die Sprache oder Bedingung

1. In der RC-Datei oder in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster mit der rechten Maustaste in der Ressource, die Sie kopieren möchten.

1. Wählen Sie **Kopie einfügen** aus dem Kontextmenü und legen Sie den folgenden:

   - Für die **Sprache** Listenfeld, wählen Sie die Sprache.

   - In der **Bedingung** geben die Bedingung.

## <a name="edit-resources"></a>Bearbeiten von Ressourcen

Verwaltete Ressourcendateien (.resx) sind XML-Dateien. Wenn Sie eine verwaltete Ressourcendatei hinzufügen, um das Projekt aus der **neues Element hinzufügen** im Dialogfeld die **verwaltete Ressourcen-Editor** wird standardmäßig geöffnet.

## <a name="import-and-export-resources"></a>-Import/Export-Ressourcen

Sie können grafische Ressourcen (Bitmaps, Symbole, Cursor und Symbolleisten), HTML-Dateien und benutzerdefinierte Ressourcen für die Verwendung in Visual C++ importieren. Die können dieselben Dateitypen aus einem Visual C++-Projekt exportieren, um Dateien zu trennen, die außerhalb der Entwicklungsumgebung verwendet werden können.

> [!NOTE]
> Ressourcentypen wie Zugriffstasten, Dialogfelder und Zeichenfolgentabellen können weder im- noch exportiert werden, da sie keine eigenständigen Dateitypen sind.

### <a name="to-import-an-individual-resource-into-your-current-resource-file"></a>So importieren Sie eine einzelne Ressource in Ihre aktuelle Ressourcendatei

1. In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste des Knotens für das Ressourcenskript (* .rc)-Datei zu dem beim Hinzufügen einer Ressource werden sollen.

1. Wählen Sie **Import** im Kontextmenü auf.

1. Suchen Sie nach dem Dateinamen der Bitmap- (.bmp), Symbol- (.ico), Cursor- (.cur), HTML- (.html) oder einer anderen zu importierenden Datei, und wählen Sie ihn aus.

1. Wählen Sie **OK** zum Hinzufügen der Ressource zur ausgewählten Datei in **Ressource** anzeigen.

   > [!NOTE]
   > Der Importvorgang funktioniert auf die gleiche Weise, und zwar unabhängig davon, welchen bestimmten Ressourcentyp Sie ausgewählt haben. Die importierte Ressource wird automatisch zum richtigen Knoten für diesen Ressourcentyp hinzugefügt.

### <a name="to-export-a-bitmap-icon-or-cursor-as-a-separate-file-for-use-outside-of-visual-c"></a>So exportieren Sie Bitmaps, Symbole oder Cursor als eine getrennte Datei (für die Verwendung außerhalb von Visual C++)

1. In **Ressource** Anzeigen der rechten Maustaste auf die Ressource, die Sie exportieren möchten.

1. Wählen Sie **exportieren** im Kontextmenü auf den aktuellen Dateinamen akzeptiert, und geben Sie einen neuen.

1. Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern, und wählen Sie möchten **exportieren**.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Erstellen von Ressourcen](../windows/how-to-create-a-resource-script-file.md)<br/>
[Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md)<br/>