---
title: Festlegen eines Cursors&#39;Hotspot "s" (Bildbearbeitung für Symbole) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.editing
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], hot spots
- hot spots
ms.assetid: a610388a-45c8-43cd-98a2-fd31f29238b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9246d7a26c9764e31cca9c861ec0a15d4792c115
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389096"
---
# <a name="setting-a-cursor39s-hot-spot-image-editor-for-icons"></a>Festlegen eines Cursors&#39;Hotspot "s" (Bildbearbeitung für Symbole)

Den Hotspot, der eine [Cursor](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md) ist der Punkt, auf die Windows verweist, in die Position des Cursors nachverfolgen. Standardmäßig wird den Hotspot auf der linken oberen Ecke des Cursors (Koordinaten 0,0) festgelegt. Die **Hotspot** -Eigenschaft in der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window) zeigt die Koordinaten des HotSpot.

### <a name="to-set-a-cursors-hot-spot"></a>Festlegen des Hotspots eines Cursors

1. Auf der [Symbolleiste der Bildbearbeitung](../windows/toolbar-image-editor-for-icons.md), klicken Sie auf die **Hotspot festlegen** Tool.

2. Klicken Sie auf das Pixel, die, das Sie als den Cursorhotspot festlegen möchten.

   Die **Hotspot** -Eigenschaft in der **Eigenschaften** Fenster zeigt die neuen Koordinaten.

   > [!TIP]
   > Wenn Sie den Cursor auf eine Symbolleisten-Schaltfläche zeigen, werden QuickInfos angezeigt. Diese Tipps können Sie die Funktion der einzelnen Schaltflächen zu identifizieren.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Keiner

## <a name="see-also"></a>Siehe auch

[Zugriffstasten](../windows/accelerator-keys-image-editor-for-icons.md)<br/>
[Symbole und Cursor: Bildressourcen für Anzeigegeräte](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)