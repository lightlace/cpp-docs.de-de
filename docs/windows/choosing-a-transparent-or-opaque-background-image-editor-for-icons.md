---
title: Auswählen eines transparenten oder deckenden Hintergrunds (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- opaque backgrounds [C++]
- colors [C++], image
- Image editor [C++], transparent or opague backgrounds
- images [C++], transparency
- images [C++], opaque background
ms.assetid: 61b743d9-c86b-405d-9a81-0806431b4363
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 77d9647fd4432bf2ab0cf9e4add2a08ce964b85a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50060077"
---
# <a name="choosing-a-transparent-or-opaque-background-image-editor-for-icons"></a>Auswählen eines transparenten oder deckenden Hintergrunds (Bildbearbeitung für Symbole)

Beim Verschieben oder kopieren eine Auswahl aus einem Image, werden alle Pixel in der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen, sind standardmäßig transparent; Sie sind nicht Pixel am Zielspeicherort erschwert.

Sie können über einen transparenten Hintergrund (Standard) wechseln, um ein nicht transparenter Hintergrund und wieder zurück. Wenn Sie eine Auswahltool verwenden, die **transparenten Hintergrund** und **nicht transparenter Hintergrund** Optionen angezeigt, der **Option** -Selektor auf die **Bildbearbeitung** Symbolleiste (siehe unten).

![Optionen im Hintergrund &#45; undurchsichtig oder durchsichtig](../windows/media/vcimageeditoropaqtranspback.gif "VcImageEditorOpaqTranspBack")<br/>
**Transparente und undurchsichtige Optionen** auf die **Symbolleiste der Bildbearbeitung**

### <a name="to-switch-between-a-transparent-and-opaque-background"></a>So wechseln Sie zwischen einem transparente und undurchsichtige-Hintergrund

1. In der **Bild-Editor** -Symbolleiste klicken Sie auf die **Option** Auswahl, und klicken Sie dann auf den entsprechenden Hintergrund:

   - `Opaque Background (O)`: Vorhandene Bild wird von allen Bereichen der Auswahl verdeckt.

   - `Transparent Background (T)`: Das vorhandene Bild zeigt Teile der Auswahl, die mit die aktuellen Hintergrundfarbe übereinstimmen.

\- oder –

- Auf der **Image** Menü aktivieren oder deaktivieren Sie **Deckend zeichnen**.

Sie können die Farbe des Hintergrunds ändern, während eine Auswahl bereits aktiv ist ändern, welche Teile des Bilds transparent sind.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Arbeiten mit Farben](../windows/working-with-color-image-editor-for-icons.md)