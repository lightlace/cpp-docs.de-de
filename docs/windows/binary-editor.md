---
title: Binär-Editor (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.binary.F1
helpviewer_keywords:
- editors, Binary
- resources [C++], editing
- resource editors [C++], Binary editor
- Binary editor
ms.assetid: 2483c48b-1252-4dbc-826b-82e6c1a0e9cb
ms.openlocfilehash: 1b5e1c16ff63c55617ee9b2bbcb47a7201635789
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451700"
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

Mit der **binäre** -Editor können Sie:

- [Eine Ressource für die Binärbearbeitung öffnen](../windows/opening-a-resource-for-binary-editing.md)

- [Binärdaten bearbeiten](../windows/editing-binary-data.md)

- [Binärdaten suchen](../windows/finding-binary-data.md)

- [Eine neue benutzerdefinierte Ressource oder Datenressource erstellen](../windows/creating-a-new-custom-or-data-resource.md)

## <a name="managed-resources"></a>Verwaltete Ressourcen

Können Sie die [bildbearbeitung](../windows/image-editor-for-icons.md) und **binäre** -Editor, um die Arbeit mit Ressourcendateien in verwalteten Projekten. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)