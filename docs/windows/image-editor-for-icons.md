---
title: Bildbearbeitung für Symbole | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/17/2018
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.cursor.F1
- vc.editors.icon.F1
- vc.editors.cursor
- vc.editors.bitmap.F1
dev_langs:
- C++
helpviewer_keywords:
- editors, images
- resource editors [C++], graphics
- Image editor [C++]
- resource editors [C++], Image editor
ms.assetid: 586d2b8b-0348-4883-a85d-1ff0ddbf14dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ecd2b3b94f04a246242a33494a124171e95cae7c
ms.sourcegitcommit: db6b2ad3195e71abfb60b62f3f015f08b0a719d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2018
ms.locfileid: "49410667"
---
# <a name="image-editor-for-icons"></a>Bildbearbeitung für Symbole

Wenn Sie auf eine Bilddatei (z. B. ico, BMP, PNG) im Projektmappen-Explorer klicken, öffnet das Bild im Bild-Editor auf die gleiche Weise, die Codedateien im Code-Editor geöffnet. Wenn eine Registerkarte Bild-Editor aktiv ist, sehen Sie Symbolleisten mit vielen Tools zum Erstellen und Bearbeiten von Bildern. Zusätzlich zu Bitmaps, Symbolen und Cursorn können Sie Bilder im GIF- oder JPEG-Format bearbeiten. Zu diesem Zweck verwenden Sie die Befehle aus dem Menü **Bild** und die Tools auf der Symbolleiste der **Bildbearbeitung** .

Von der Bildbearbeitung werden die folgenden Aufgaben unterstützt:

- [Bearbeiten von grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)

- [Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)

- [Arbeiten mit Symbolen und Cursorn: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)

- [Verwenden von Zugriffstasten für den Grafik-Editor](../windows/accelerator-keys-image-editor-for-icons.md)

Die **Bildbearbeitung** Fenster zeigt zwei Ansichten eines Bilds mit einem Fensterteiler die zwei Bereiche. Zum Ändern der relativen Größe der Fensterbereiche kann der Fensterteiler seitlich gezogen werden. Der aktive Bereich ist von einem Markierungsrahmen umgeben.

Die **Bildbearbeitung** Fenster entsprechend Ihren Anforderungen und Prioritäten angepasst werden kann. Sie können den [Vergrößerungsfaktor ändern](../windows/changing-the-magnification-factor-image-editor-for-icons.md) und das [Pixelraster ein- oder ausblenden](../windows/displaying-or-hiding-the-pixel-grid-image-editor-for-icons.md).

> [!NOTE]
> Mithilfe der **Bildbearbeitung**, können Sie die 32-Bit-Images anzeigen, aber nicht bearbeiten.

## <a name="visual-studio-image-library"></a>Visual Studio-Bildbibliothek

Sie können kostenlos herunterladen der **Visual Studio-Bildbibliothek** enthält zahlreiche Animationen, Bitmaps und Symbole, die Sie in Ihren Anwendungen verwenden können. Weitere Informationen über das Herunterladen der Bibliothek finden Sie unter [Die Visual Studio-Bildbibliothek](/visualstudio/designers/the-visual-studio-image-library).

## <a name="managed-resources"></a>Verwaltete Ressourcen

Können Sie die **Image** Editor und die [binär-Editor](binary-editor.md) , Bearbeitung von Ressourcendateien in verwalteten Projekten möglich. Bei den zu bearbeitenden verwalteten Ressourcen muss es sich um verknüpfte Ressourcen handeln. Das Bearbeiten eingebetteter Ressourcen wird von den Visual Studio-Ressourcen-Editoren nicht unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Ressourcen-Editor](../windows/resource-editors.md)<br/>
[Symbole](https://msdn.microsoft.com/library/windows/desktop/ms646973.aspx)