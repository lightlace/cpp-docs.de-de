---
title: Bearbeiten von Bestandteilen eines Bilds (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], editing images
- Clipboard [C++], pasting
- images [C++], editing
- images [C++], deleting selected parts
- images [C++], copying selected parts
- images [C++], moving selected parts
- images [C++], dragging and replicating selected parts
- images [C++], pasting into
- graphics [C++], editing
ms.assetid: ff4f5fef-71a4-4fd8-825e-049399fed391
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9340180049d85b1b5385d49c7b358c3fd791ce9d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391474"
---
# <a name="editing-parts-of-an-image-image-editor-for-icons"></a>Bearbeiten von Bestandteilen eines Bilds (Bildbearbeitung für Symbole)

Können Sie standard Bearbeitungsvorgänge ausführen – Ausschneiden, kopieren, löschen und verschieben, auf eine [Auswahl](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md), ob die Auswahl auf das gesamte Bild oder nur eines Teils davon ist. Da die **Image** Editor verwendet die **Windows-Zwischenablage**, Sie können Bilder zwischen übertragen der **Image** -Editor und andere Anwendungen für Windows.

Darüber hinaus können Sie die Auswahl, Größe ändern, ob es sich um das gesamte Bild oder nur einen Teil enthält.

### <a name="to-cut-the-current-selection-and-move-it-to-the-clipboard"></a>So schneiden Sie die aktuelle Auswahl und verschieben Sie es in die Zwischenablage

1. Klicken Sie auf **Ausschneiden** auf die **bearbeiten** Menü.

### <a name="to-copy-the-selection"></a>Um die Auswahl kopieren

1. Positionieren Sie den Zeiger in einen Rahmen oder an einer beliebigen Stelle auf, mit Ausnahme der Ziehpunkte.

2. Halten Sie die **STRG** gedrückt, während Sie die Auswahl in eine neue Position ziehen. Der Bereich der ursprünglichen Auswahl ist unverändert.

3. Um die Auswahl in das Abbild an dessen aktuellen Speicherort zu kopieren, klicken Sie außerhalb des Cursors für die Auswahl.

### <a name="to-paste-the-clipboard-contents-into-an-image"></a>Der Inhalt der Zwischenablage in ein Bild einfügen

1. Von der **bearbeiten** Menü wählen **einfügen**.

   Der Inhalt der Zwischenablage, von der Markierungsrahmen umgeben werden in der oberen linken Ecke des Bereichs angezeigt.

2. Positionieren Sie den Zeiger in einen Rahmen, und ziehen Sie das Bild an die gewünschte Position auf dem Bild.

3. Um das Bild an seinem neuen Standort zu verankern, klicken Sie außerhalb der Markierungsrahmen umgeben.

### <a name="to-delete-the-current-selection-without-moving-it-to-the-clipboard"></a>Um die aktuelle Auswahl zu löschen, ohne ihn zu verschieben in die Zwischenablage

1. Von der **bearbeiten** Menü wählen **löschen**.

   Der ursprüngliche Bereich der Auswahl wird mit der aktuellen Hintergrundfarbe gefüllt.

   > [!NOTE]
   > Sie erreichen die **Ausschneiden**, **Kopie**, **einfügen**, und **löschen** Befehle, indem Sie mit der rechten Maustaste auf die **Ressourcenansicht** Fenster.

### <a name="to-move-the-selection"></a>Um die Auswahl verschieben

1. Positionieren Sie den Zeiger in einen Rahmen oder an einer beliebigen Stelle auf, mit Ausnahme der Ziehpunkte.

2. Ziehen Sie die Auswahl an die neue Position.

3. Um die Auswahl an die neue Position in das Image zu verankern, klicken Sie außerhalb des Rahmens für die Auswahl.

Weitere Informationen zum Zeichnen mit einer Auswahl, finden Sie unter [Erstellen von benutzerdefinierten Pinseln](../windows/creating-a-custom-brush-image-editor-for-icons.md).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)