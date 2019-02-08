---
title: 'Vorgehensweise: Kopieren von Ressourcen (C++)'
ms.date: 11/04/2016
f1_keywords:
- vc.resvw.resource.copying
- vs.resvw.resource.copying
- vc.resvw.resource.changing
helpviewer_keywords:
- resources [C++], moving between files
- resources [C++], copying
- resource files [C++], copying or moving resources between
- resource files [C++], tiling
- .rc files [C++], copying resources between
- rc files [C++], copying resources between
- Language property [C++]
ms.assetid: 65f523e8-017f-4fc6-82d1-083c56d9131f
ms.openlocfilehash: 772c9b905d4cb0c4e2ccab9ec51aa02860b2db32
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849660"
---
# <a name="how-to-copy-resources-c"></a>Vorgehensweise: Kopieren von Ressourcen (C++)

Sie können Ressourcen in eine andere aus einer Datei kopieren, ohne sie zu ändern, oder Sie können die Sprache oder Bedingung einer Ressource während des Kopiervorgangs ändern.

Sie können Ressourcen problemlos aus einer vorhandenen Ressource oder die ausführbare Datei in Ihre aktuelle Ressourcendatei kopieren. Um Ressourcen zu kopieren, öffnen Sie beide Dateien, die mit Ressourcen zur gleichen Zeit Sie und ziehen Sie Elemente aus einer Datei in eine andere oder kopieren und fügen Sie zwischen den beiden Dateien. Diese Methode funktioniert für Ressourcenskriptdateien (RC) und Ressourcendateien für die Vorlage (.rct) sowie als ausführbare Dateien (.exe).

> [!NOTE]
> Visual C++ enthält Beispiel-Ressourcendateien, die Sie in Ihrer eigenen Anwendung verwenden können. Weitere Informationen finden Sie unter [CLIPART: Allgemeine Ressourcen](https://github.com/Microsoft/VCSamples).

Sie können die Drag & Drop-Methode verwenden, RC-Dateien, die geöffnet sind [außerhalb des Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).

## <a name="to-copy-resources-between-files-using-the-drag-and-drop-method"></a>So kopieren Sie Ressourcen zwischen den Dateien, die mithilfe der Drag & Drop-Methode

1. Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [eine Ressourcenskriptdatei Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Öffnen Sie beispielsweise Source1.rc und Source2.rc.

1. Wählen Sie in der ersten RC-Datei die Ressource, die Sie kopieren möchten. Z. B. in `Source1.rc`Option **IDD_DIALOG1**.

1. Halten Sie die **STRG** gedrückt, und ziehen Sie die Ressource in der zweiten RC-Datei. Ziehen Sie z. B. **IDD_DIALOG1** aus `Source1.rc` zu `Source2.rc`.

   > [!NOTE]
   > Ziehen die Ressource ohne gedrückt der **STRG** drücken, das verschoben wird, die Ressource, statt es zu kopieren.

## <a name="to-copy-resources-using-copy-and-paste"></a>Zum Kopieren von Ressourcen mithilfe von kopieren und einfügen

1. Öffnen Sie beide Ressourcendateien eigenständig (Weitere Informationen finden Sie unter [eine Ressourcenskriptdatei Datei außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)). Beispielsweise Source1.rc und Source2.rc.

1. In der Quelldatei, die von dem Sie eine Ressource zu kopieren möchten (z. B. `Source1.rc`) mit der rechten Maustaste auf eine Ressource, und wählen Sie **Kopie** aus dem Kontextmenü.

1. Mit der rechten Maustaste in der Ressourcendatei in die Sie die Ressource einfügen möchten (z. B. `Source2.rc`). Wählen Sie **einfügen** aus dem Kontextmenü.

   > [!NOTE]
   > Sie können keine drag und drop, kopieren, Ausschneiden, oder fügen Sie zwischen Ressourcendateien im Projekt (**Ressourcenansicht**) und eigenständige RC-Dateien (die im Dokumentfenster geöffnet). In früheren Versionen des Produkts können Sie dazu.

   > [!NOTE]
   > Um Konflikte mit Symbolnamen oder Werten in die vorhandene Datei zu vermeiden, kann Visual C++ Symbolwert der übertragenen Ressource oder Symbolnamens und-Werts ändern, wenn Sie ihn in die neue Datei kopieren.

## <a name="to-change-the-language-or-condition-of-a-resource-while-copying-c"></a>So ändern Sie die Sprache oder Bedingung einer Ressource während des Kopiervorgangs (C++)

Beim Kopieren in eine Ressource können Sie ihre Sprachen- und/oder Bedingungseigenschaft ändern.

- Die Ressourcensprache ermittelt lediglich die Sprache für die Ressource. Die Sprache wird verwendet, indem [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) können Sie die Ressource zu identifizieren, für die Sie suchen. (Allerdings Ressourcen können Unterschiede für jede Sprache, die nicht mit Text verknüpft sind, erstellt z. B. Tastenkombinationen, die möglicherweise nur auf einer japanischen Tastatur funktionieren oder eine Bitmap, die nur für Chinesisch gilt geeignet wären.)

- Die Bedingung einer Ressource stellt ein definiertes Symbol dar, das eine Bedingung angibt, unter der diese bestimmte Ressourcenkopie zu verwenden ist.

Sprache und Bedingung einer Ressource werden im Arbeitsbereichsfenster nach dem Ressourcennamen in Klammern angezeigt. In diesem Beispiel verwendet die Ressource mit dem Namen IDD_AboutBox Finnisch als Sprache und XX33 als Bedingung aus.

```cpp
IDD_AboutBox (Finnish - XX33)
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>So kopieren Sie eine vorhandene Ressource und ändern die Sprache oder Bedingung

1. In der RC-Datei oder in der [Ressourcenansicht](../windows/resource-view-window.md) Fenster mit der rechten Maustaste in der Ressource, die Sie kopieren möchten.

1. Wählen Sie **Kopie einfügen** aus dem Kontextmenü.

1. In der **Ressourcenkopie** Dialogfeld:

   - Für die **Sprache** Listenfeld, wählen Sie die Sprache.

   - In der **Bedingung** geben die Bedingung.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Vorgehensweise: Öffnen einer Ressourcenskriptdatei außerhalb eines Projekts (eigenständig)](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md)<br/>
