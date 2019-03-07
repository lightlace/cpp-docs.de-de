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
ms.openlocfilehash: 28127ea89fdba1b70988ced1d6004c0f914c66e2
ms.sourcegitcommit: b4645761ce5acf8c2fc7a662334dd5a471ea976d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/07/2019
ms.locfileid: "57563042"
---
# <a name="how-to-manage-resources-c"></a>Vorgehensweise: Verwalten von Ressourcen (C++)

## <a name="copy-and-edit-resources"></a>Kopieren und Bearbeiten von Ressourcen

Sie können Ressourcen aus einer Datei in eine andere kopieren, ohne sie ändern oder das Ändern der Sprache oder Bedingung einer Ressource während des Kopiervorgangs.

Sie können Ressourcen problemlos aus einer vorhandenen Ressource oder die ausführbare Datei in Ihre aktuelle Ressourcendatei kopieren. Um Ressourcen zu kopieren, öffnen Sie beide Dateien, die mit Ressourcen zur gleichen Zeit Sie und ziehen Sie Elemente aus einer Datei in eine andere oder kopieren und fügen Sie zwischen den beiden Dateien. Diese Methode funktioniert für Ressourcenskriptdateien (RC) und Ressourcendateien für die Vorlage (.rct) sowie als ausführbare Dateien (.exe).

> [!NOTE]
> Visual C++ enthält Beispiel-Ressourcendateien, die Sie in Ihrer eigenen Anwendung verwenden können. Weitere Informationen finden Sie unter [CLIPART: Allgemeine Ressourcen](https://github.com/Microsoft/VCSamples).

Sie können keine drag und drop, kopieren, Ausschneiden, oder fügen Sie zwischen Ressourcendateien im Projekt (**Ressourcenansicht**) und eigenständige RC-Dateien im Dokumentfenster zu öffnen. In früheren Versionen des Produkts können Sie dazu. Verwenden Sie die Drag & Drop-Methode nur RC-Dateien, die außerhalb des Projekts geöffnet sind.

### <a name="to-copy-resources"></a>So kopieren Sie Ressourcen

1. Öffnen Sie beide Ressourcendateien eigenständig (finden Sie unter Vorgehensweise [zum Öffnen einer Ressourcenskriptdatei](/how-to-create-a-resource-script-file#use-resource-script-files)). Öffnen Sie z. B. *Source1.rc* und *Source2.rc*.

1. In der ersten RC-Datei, entweder:

   - Verwenden Sie die Drag & Drop-Methode

      1. Wählen Sie die Ressource, die Sie kopieren möchten. Z. B. in *Source1.rc*Option **IDD_DIALOG1**.

      1. Halten Sie die **STRG** gedrückt, und ziehen Sie die Ressource in der zweiten RC-Datei. Ziehen Sie z. B. **IDD_DIALOG1** aus *Source1.rc* zu *Source2.rc*.

         > [!TIP]
         > Ziehen die Ressource ohne gedrückt der **STRG** drücken, das verschoben wird, die Ressource, statt es zu kopieren.

   - Kopieren und einfügen

      1. Mit der rechten Maustaste in der Ressource mit Kopieren (z. B. *Source1.rc*), und wählen Sie **Kopie**.

      1. Mit der rechten Maustaste in der Ressourcendatei in die Sie die Ressource einfügen möchten (z. B. *Source2.rc*), und wählen Sie **einfügen**.

> [!NOTE]
> Um Konflikte mit Symbolnamen oder Werten in die vorhandene Datei zu vermeiden, kann Visual C++ Symbolwert der übertragenen Ressource oder Symbolnamens und-Werts ändern, wenn Sie ihn in die neue Datei kopieren.

Beim Kopieren in eine Ressource können Sie ihre Sprachen- und/oder Bedingungseigenschaft ändern.

- Die Sprache der Ressource gibt an, die von verwendete Sprache [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) können Sie die Ressource zu identifizieren, für die Sie suchen. Ressourcen können Unterschiede für jede Sprache, die nicht mit Text verknüpft sind, erstellt z. B. Tastenkombinationen, die möglicherweise nur auf einer japanischen Tastatur funktionieren oder eine Bitmap, die nur für Chinesisch gilt geeignet wären.

- Die Bedingung einer Ressource stellt ein definiertes Symbol dar, das eine Bedingung angibt, unter der diese bestimmte Ressourcenkopie zu verwenden ist.

Die Sprache und Bedingung einer Ressource in Klammern angezeigt, nach dem Namen der Ressource in der **Arbeitsbereich** Fenster. Hier für die Ressource mit dem Namen `IDD_AboutBox` verwendet `Finnish` ist als seine Sprache und der Bedingung `XX33`:

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>So kopieren Sie eine vorhandene Ressource und ändern die Sprache oder Bedingung

In der *RC* Datei oder in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster mit der rechten Maustaste in der Ressource, die Sie verwenden möchten, kopieren, und wählen **Kopie einfügen**. Legen Sie Sie dann die folgenden Schritte aus:

- Für die **Sprache** Listenfeld, wählen Sie die Sprache.

- In der **Bedingung** geben die Bedingung.

### <a name="to-edit-resources"></a>Bearbeiten von Ressourcen

Verwaltete Ressourcendateien (.resx) sind XML-Dateien. Wenn Sie eine verwaltete Ressourcendatei hinzufügen, um das Projekt aus der **neues Element hinzufügen** im Dialogfeld die **verwaltete Ressourcen-Editor** wird standardmäßig geöffnet.

## <a name="import-and-export-resources"></a>-Import/Export-Ressourcen

Sie können grafische Ressourcen (Bitmaps, Symbole, Cursor und Symbolleisten), HTML-Dateien und benutzerdefinierte Ressourcen für die Verwendung in Visual C++ importieren. Die können dieselben Dateitypen aus einem Visual C++-Projekt exportieren, um Dateien zu trennen, die außerhalb der Entwicklungsumgebung verwendet werden können.

> [!NOTE]
> Ressourcentypen wie Zugriffstasten, Dialogfelder und Zeichenfolgentabellen können nicht exportiert werden, weil sie keine eigenständigen Dateitypen sind oder importiert werden.

### <a name="to-import-a-resource-into-the-resource-script-file"></a>So importieren Sie eine Ressource in die Ressourcenskriptdatei

1. In [Ressourcenansicht](../windows/resource-view-window.md) mit der rechten Maustaste des Knotens der Ressourcendatei für die Ressourcenskriptdatei (.rc), Sie fügen eine Ressource, und wählen möchten **Import**.

1. Suchen Sie, und wählen Sie den Dateinamen der Bitmap-(.bmp), Symbol-(.ico), Cursor-(.cur), html-Datei (HTML) oder andere Datei zu importieren.

1. Wählen Sie **OK** auf die Ressource die Ressourcenskriptdatei hinzuzufügen.

> [!NOTE]
> Der Importvorgang funktioniert identisch unabhängig davon, welche Ressourcentyp Sie, ausgewählt haben. Die importierte Ressource wird automatisch zum richtigen Knoten des Ressourcentyps hinzugefügt.

### <a name="to-export-a-resource-for-use-outside-of-visual-c"></a>So exportieren Sie eine Ressource für die Verwendung außerhalb von Visual C++

1. In [Ressourcenansicht](../windows/resource-view-window.md), mit der rechten Maustaste in der Ressource, die Sie verwenden möchten, exportieren, und wählen Sie **exportieren**. Sie können den aktuellen Dateinamen akzeptieren oder geben Sie einen neuen.

1. Navigieren Sie zu dem Ordner, in dem Sie die Datei speichern, und wählen Sie möchten **exportieren**.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Vorgehensweise: Ressourcen erstellen](../windows/how-to-create-a-resource-script-file.md)<br/>
[Vorgehensweise: Einfügen von Ressourcen zur Kompilierungszeit](../windows/how-to-include-resources-at-compile-time.md)<br/>