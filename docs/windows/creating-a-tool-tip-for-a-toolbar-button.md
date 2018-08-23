---
title: Erstellen einer QuickInfo für eine Symbolleisten-Schaltfläche | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tool tips [C++], adding to toolbar buttons
- "\nin tool tip"
- toolbar buttons [C++], tool tips
- buttons [C++], tool tips
- Toolbar editor, creating tool tips
ms.assetid: 0af65342-fd78-4e78-8d0d-dc68f7fc462e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aef763e20df3d8b19326a008706a45cc5508cd9c
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600109"
---
# <a name="creating-a-tool-tip-for-a-toolbar-button"></a>Erstellen einer QuickInfo für eine Symbolleisten-Schaltfläche

### <a name="to-create-a-tool-tip"></a>Zum Erstellen einer QuickInfo

1. Wählen Sie die Symbolleisten-Schaltfläche.

2. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window)in die **Eingabeaufforderung** Eigenschaftenfeld, fügen Sie eine Beschreibung der Schaltfläche für die Statusleiste, nachdem die Nachricht, fügen `\n` und den Namen des Tools Tipp.

Ein gängiges Beispiel für eine QuickInfo ist die **Drucken** Schaltfläche **WordPad**:

1. Open **WordPad**.

2. Zeigen Sie den Mauszeiger auf die **Drucken** Symbolleisten-Schaltfläche.

3. Beachten Sie, dass das Wort `Print` nun unverankert ist, unter der Maus.

4. Sehen Sie sich die Statusleiste (ganz unten auf der die **WordPad** Fenster): Beachten Sie, dass es jetzt der Text zeigt `Prints the active document`.

Die `Print` in **Schritt 3** ist der "Tool-Tipp-Name", und die `Prints the active document` aus **Schritt 4** lautet "Beschreibung der Schaltfläche für die Statusleiste."

Wenn Sie möchten diesen Effekt mit der **Symbolleiste** -Editor Festlegen der **Eingabeaufforderung** Eigenschaft `Prints the active document\nPrint`.

> [!NOTE]
> Können Sie bearbeiten, Aufforderungstext mithilfe der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Weitere Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Anforderungen

MFC oder ATL

## <a name="see-also"></a>Siehe auch

[Erstellen, Verschieben und Bearbeiten von Schaltflächen der Symbolleiste](../windows/creating-moving-and-editing-toolbar-buttons.md)  
[Symbolleisten-Editor](../windows/toolbar-editor.md)