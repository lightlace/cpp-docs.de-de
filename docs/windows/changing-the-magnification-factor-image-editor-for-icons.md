---
title: Ändern des Vergrößerungsfaktors (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Image editor [C++], magnification
ms.assetid: d1b0c9e0-fe54-4b2a-b75e-ffa0fa7c8cd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ee905c88a9dc2cdd8d05e3b60bbc07259c17e850
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385559"
---
# <a name="changing-the-magnification-factor-image-editor-for-icons"></a>Ändern des Vergrößerungsfaktors (Bildbearbeitung für Symbole)

Standardmäßig zeigt die Bild-Editor die Ansicht im linken Bereich auf die tatsächliche Größe und die Ansicht im rechten Bereich mit der tatsächlichen Größe 6-Mal. Die Vergrößerungsfaktor (in der Statusleiste am unteren Rand des Arbeitsbereichs) ist das Verhältnis zwischen der tatsächlichen Größe des Bilds und die angezeigte Größe. Der Standardfaktor 6 und der Bereich liegt zwischen 1 und 10.

### <a name="to-change-the-magnification-factor"></a>Ändern des Vergrößerungsfaktors

1. Wählen Sie die **Bildbearbeitung** Bereich, dessen Vergrößerungsfaktor ändern möchten.

2. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md), klicken Sie auf den Pfeil rechts neben der [Tool vergrößern](../windows/toolbar-image-editor-for-icons.md) , und wählen Sie im Untermenü des Vergrößerungsfaktors: **1 X**, **2 X**, **6 X**, oder **8 X**.

   > [!NOTE]
   > Auf einen Vergrößerungsfaktor nicht aufgelistet, die der **Magnify** tool können Sie die Zugriffstasten.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Fensterbereiche](../windows/window-panes-image-editor-for-icons.md)