---
title: Erstellen von benutzerdefinierten Pinseln (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- colors [C++], brush
- brushes, colors
- brushes, creating custom
- images [C++], creating custom brushes
- graphics [C++], custom brushes
- custom brushes
ms.assetid: 750881aa-6f47-4de9-8ca6-a7a12afc6383
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd4a25b208232c8a0923e33156730fc5612219a5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388198"
---
# <a name="creating-a-custom-brush-image-editor-for-icons"></a>Erstellen von benutzerdefinierten Pinseln (Bildbearbeitung für Symbole)

Ein benutzerdefiniertes Pinsels wird einen rechteckigen Teil eines Bilds, das Sie weitermachen und wie eines der **Image** vorgefertigte Pinsel Editor. Alle Vorgänge, die Sie für eine Auswahl ausführen können, können Sie für einen benutzerdefinierten Pinsel ebenfalls ausführen.

### <a name="to-create-a-custom-brush-from-a-portion-of-an-image"></a>Zum Erstellen von benutzerdefinierten Pinseln aus einem Teil eines Bilds

1. [Wählen Sie den Teil des Bilds](../windows/selecting-an-area-of-an-image-image-editor-for-icons.md) , die für den Pinsel verwendet werden sollen.

2. Enthält die **UMSCHALT** gedrückt, klicken Sie auf die Markierung und ziehen Sie sie über das Image.

   \- oder –

3. Von der **Image** Menü wählen **Auswahl als Pinsel verwenden**.

   Ihre Auswahl wird es sich um einen benutzerdefinierten Pinsel, der die Farben in der Auswahl auf das Bild verteilt. Kopien der Auswahl bleiben entlang des Pfads ziehen. Sie ziehen, desto langsamer, desto mehr Kopien erfolgen.

   > [!NOTE]
   > Klicken auf die **Auswahl als Pinsel verwenden** ohne zuerst auszuwählen einen Teil des Bilds, das gesamte Bild als Pinsel verwendet wird. Das Ergebnis der Verwendung von benutzerdefinierten Pinseln hängt außerdem, ob Sie ausgewählt haben eine [undurchsichtig oder Transparent Background](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

Pixel in einem benutzerdefinierten Pinsel, die mit die aktuellen Hintergrundfarbe übereinstimmen, sind normalerweise transparent: sie sind nicht auf das vorhandene Bild zeichnen. Sie können dieses Verhalten ändern, sodass Hintergrundfarbe Pixel auf das vorhandene Bild zu zeichnen.

Sie können den benutzerdefinierten Pinsel wie einen Zeitstempel oder eine Schablone verwenden, erstellen Sie eine Vielzahl von Spezialeffekte zu erzeugen.

### <a name="to-draw-custom-brush-shapes-in-the-background-color"></a>Zum Zeichnen von benutzerdefinierten Pinseln-Formen in die Hintergrundfarbe

1. [Wählen Sie einen Hintergrund undurchsichtig oder durchsichtig](../windows/choosing-a-transparent-or-opaque-background-image-editor-for-icons.md).

2. [Festlegen der Hintergrundfarbe](../windows/selecting-foreground-or-background-colors-image-editor-for-icons.md) auf die Farbe, in dem Sie zeichnen möchten.

3. Positionieren Sie den benutzerdefinierten Pinsel, in dem Sie zeichnen möchten.

4. Klicken Sie auf der rechten Maustaste. Einem nicht transparenten Bereiche der benutzerdefinierten Pinsel sind in die Hintergrundfarbe gezeichnet wird.

### <a name="to-double-or-halve-the-custom-brush-size"></a>Doppelklicken oder die Größe des benutzerdefinierten Pinsels halbieren

1. Drücken Sie die **Pluszeichen** (**+**)-Taste, um die Pinselgröße doppelklicken oder die **Minuszeichen (-)** (**-**) um sie zu halbieren .

### <a name="to-cancel-the-custom-brush"></a>Um den benutzerdefinierten Pinsel abzubrechen.

1. Drücken Sie **Esc** , oder wählen Sie einen anderen Zeichenwerkzeug aus.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Bearbeiten von Grafischen Ressourcen](../windows/editing-graphical-resources-image-editor-for-icons.md)<br/>
[Bildbearbeitung für Symbole](../windows/image-editor-for-icons.md)