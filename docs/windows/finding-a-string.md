---
title: Suchen eine Zeichenfolgenressource (C++) | Microsoft-Dokumentation
ms.date: 11/04/2016
f1_keywords:
- vc.editors.string
helpviewer_keywords:
- strings [C++], searching
- strings [C++]
ms.assetid: c2497173-f356-4f77-97d6-f0ac41782510
ms.openlocfilehash: 0e6d8ac8027028377e903a9e0a3c89238a9862a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585924"
---
# <a name="finding-a-string-resource-c"></a>Suchen eine Zeichenfolgenressource (C++)

Sie können eine oder mehrere Zeichenfolgen in der Zeichenfolgentabelle suchen und verwenden Sie [reguläre Ausdrücke](/visualstudio/ide/using-regular-expressions-in-visual-studio) mit der **in Dateien suchen** Befehl (**bearbeiten** Menü), suchen Sie alle Vorkommnisse von Zeichenfolgen die einem Muster entsprechen.

### <a name="to-find-a-string-in-the-string-table"></a>Nach einer Zeichenfolge in der Zeichenfolgentabelle

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Auf der **bearbeiten** Menü klicken Sie auf **suchen und Ersetzen**, wählen Sie dann **finden**.

3. In der **Suchen nach** Feld, wählen Sie einen früheren Suchbegriff aus der Dropdown-Liste aus, oder geben Sie die Beschriftung Text bzw. Ressourcenidentifizierer der Zeichenfolge gesucht werden soll.

4. Aktivieren Sie keines der **finden** Optionen.

5. Klicken Sie auf **Weitersuchen**.

   > [!TIP]
   > Verwenden Sie zum Verwenden von regulärer Ausdrücken beim Durchsuchen von Dateien die **in Dateien suchen** Befehl. Geben Sie einen regulären Ausdruck einem Muster entsprechen, oder klicken Sie auf die Schaltfläche rechts neben der **Suchen nach** Feld, um eine Liste von regulären Suchausdrücken anzuzeigen. Wenn Sie einen Ausdruck aus dieser Liste auswählen, wird dieser als Suchtext im der **Suchen nach** Feld. Wenn Sie reguläre Ausdrücke verwenden, werden Sie sicher, dass die **verwenden: reguläre Ausdrücke** das Kontrollkästchen aktiviert ist.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)