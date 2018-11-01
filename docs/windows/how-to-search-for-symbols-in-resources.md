---
title: 'Vorgehensweise: Symbolsuche in Ressourcen (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- symbols [C++], finding
- resources [C++], searching for symbols
ms.assetid: 6efef8e8-d0d4-4c49-b895-314974e7791a
ms.openlocfilehash: b289fa1c2e5e5e1997c5024b21cae3d7a22b2b8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655987"
---
# <a name="how-to-search-for-symbols-in-resources-c"></a>Vorgehensweise: Symbolsuche in Ressourcen (C++)

### <a name="to-find-symbols-in-resources"></a>So suchen Sie Symbole in Ressourcen

1. Von der **bearbeiten** Menü wählen **Suchsymbol**.

2. In der [Suchsymbol-Dialogfeld](/visualstudio/ide/go-to)in die **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown Liste aus, oder geben Sie die Zugriffstaste, die Sie (z. B. ID_ACCEL1) suchen möchten.

   > [!TIP]
   > Mit [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) für die Suche, müssen Sie verwenden die [Befehl in Dateien suchen](/visualstudio/ide/reference/find-command) aus der **bearbeiten** Menü anstelle von der **Suchsymbol**Befehl. Um reguläre Ausdrücke zu aktivieren, müssen Sie die **verwenden: reguläre Ausdrücke** Kontrollkästchen der [suchen (Dialogfeld)](/visualstudio/ide/finding-and-replacing-text). Anschließend können Sie auf, die nach-rechts Schaltfläche rechts neben der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im der **Suchen nach** Feld.

3. Aktivieren Sie keines der **finden** Optionen.

4. Klicken Sie auf **Weitersuchen**.

   > [!NOTE]
   > Die Suche nach Symbolen in Zeichenfolgen-, Zugriffstasten- oder Binärressourcen wird nicht unterstützt.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, die Zugriff auf Ressourcen Zeichenfolgen zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcen auf Eigenschaften.

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Symbole: Ressourcenbezeichner](../windows/symbols-resource-identifiers.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Ressourcen-Editor](../windows/resource-editors.md)