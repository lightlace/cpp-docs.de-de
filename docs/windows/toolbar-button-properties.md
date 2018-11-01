---
title: Eigenschaften von Symbolleisten-Schaltflächen (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- size, toolbar buttons
- toolbar buttons [C++], setting properties
- Toolbar editor [C++], toolbar button properties
- status bars [C++], active toolbar button text
- command IDs, toolbar buttons
- width, toolbar buttons
ms.assetid: b2705814-7c5d-4f24-8f77-07559b0cdda2
ms.openlocfilehash: f20556ac088180ceb1ed979c3e02ffc465b41c7b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665369"
---
# <a name="toolbar-button-properties-c"></a>Eigenschaften von Symbolleisten-Schaltflächen (C++)

Die Eigenschaften einer Symbolleisten-Schaltfläche sind:

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|**ID**|Definiert die ID für die Schaltfläche. Die Dropdown-Liste enthält allgemeine **ID** Namen.|
|**Breite**|Legt die Breite der Schaltfläche fest. 16 Pixel wird empfohlen.|
|**Höhe**|Legt die Höhe der Schaltfläche fest. Beachten Sie, dass die Höhe einer Schaltfläche ändert sich die Höhe aller Schaltflächen auf der Symbolleiste. 15 Pixel wird empfohlen.|
|**Eingabeaufforderung**|Definiert die Nachricht in der Statusleiste angezeigt. Hinzufügen von \n und einen Namen hinzugefügt, Symbolleisten-Schaltfläche eine QuickInfo. Weitere Informationen finden Sie unter [Erstellen einer QuickInfo](../windows/creating-a-tool-tip-for-a-toolbar-button.md).|

**Breite** und **Höhe** gelten für alle Schaltflächen. Eine Bitmap, die zum Erstellen einer Symbolleiste verwendet wird, hat eine maximale Breite von 2048. Also, wenn Sie die Schaltflächenbreite auf 512 festlegen, können Sie nur vier Schaltflächen haben, und wenn Sie die Breite auf 513 festlegen, Sie können Sie nur drei Schaltflächen verwenden.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Ändern der Eigenschaften einer Symbolleisten-Schaltfläche](../windows/changing-the-properties-of-a-toolbar-button.md)<br/>
[Symbolleisten-Editor](../windows/toolbar-editor.md)