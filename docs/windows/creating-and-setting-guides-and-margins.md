---
title: Erstellen und Festlegen von führt und die Ränder | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- guides, clearing
- guides
- Dialog editor, guides and margins
- dialog box controls, placement
- controls [C++], guides and margins
- guides, creating
- guides, moving
- margins, moving
ms.assetid: fafa4545-8f00-436f-b590-300e76601156
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2fedae08467243c0fe981b287e63f4e2e041d910
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589165"
---
# <a name="creating-and-setting-guides-and-margins"></a>Erstellen und Festlegen von Führungslinien und Rändern

Ob Sie Steuerelemente verschieben, Hinzufügen von Steuerelementen, oder den aktuellen Layout neu anordnen, Anleitungen helfen ausrichten Sie Steuerelemente in einem Dialogfeld genau. Anleitungen, die als blaue gepunktete Linien angezeigt, über das Dialogfeld im Editor, und entsprechende Pfeile die Lineale angezeigt (am Anfang und am linken Rand der **Dialogfeld** Editor).

Wenn Sie ein Dialogfeld erstellen, werden vier Ränder bereitgestellt. Ränder werden geänderte Anleitungen, die als blaue gepunktete Linien angezeigt werden.

### <a name="to-create-a-guide"></a>Um eine Anleitung zu erstellen.

1. Dem Lineal klicken Sie auf einmal, um eine Anleitung zu erstellen. (Nur einem Klick erstellt ein neues Handbuch; Doppelklicken startet die [Handbuch Einstellungen (Dialogfeld)](../windows/guide-settings-dialog-box.md) in dem Sie Einstellungen für Führungslinien angeben können.)

### <a name="to-set-a-guide"></a>Eine Führungslinie festlegen

1. Klicken Sie auf das Dialogfeld klicken Sie auf der Anleitung, und ziehen Sie es an eine neue Position. (Sie können auch den Pfeil in der zugehörigen Handbuch ziehen das Lineal klicken.)

   Die Koordinaten des Handbuchs werden in der Statusleiste am unteren Rand des Fensters und auf dem Lineal angezeigt. Zeigen Sie auf den Pfeil auf das Lineal, um die genaue Position des Handbuchs anzuzeigen.

### <a name="to-delete-a-guide"></a>So löschen Sie eine Führungslinie

1. Ziehen Sie das Handbuch aus das Dialogfeld ein.

\- oder –

- Ziehen Sie die entsprechenden Pfeil vom Lineal.

### <a name="to-move-margins"></a>So verschieben Sie Ränder

1. Ziehen Sie den Rand auf die neue Position ein.

   Um einen Rand zu machen, verschieben Sie den Rand zu einer Position 0 (null). Schalten Sie wieder auf den Rand, platzieren Sie den Mauszeiger über des Rands der Nullposition, und verschieben Sie den Rand in Position.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Modi des Dialog-Editors (Führungslinien und Raster)](../windows/dialog-editor-states-guides-and-grids.md)  
[Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)