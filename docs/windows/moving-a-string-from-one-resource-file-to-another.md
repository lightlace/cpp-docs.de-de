---
title: Verschieben von Zeichenfolgen aus einer Ressourcendatei mit einem anderen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files [C++], moving strings
- string editing, moving strings between resources
- String editor [C++], moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1255eb0fc00d1b134335807a1f20e6761c49ec90
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064471"
---
# <a name="moving-a-string-from-one-resource-file-to-another-c"></a>Verschieben von Zeichenfolgen aus einer Ressourcendatei mit einem anderen (C++)

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Eine Zeichenfolge aus einer Ressource-Skriptdatei auf einen anderen zu verschieben.

1. Öffnen Sie die Zeichenfolgentabellen in beide RC-Dateien ein. (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Mit der rechten Maustaste in der Zeichenfolge, die Sie verschieben möchten und wählen Sie **Ausschneiden** aus dem Kontextmenü.

3. Platzieren Sie den Cursor in der Ziel- **Zeichenfolgen-Editor** Fenster.

4. In der RC-Datei in das Sie verschieben, die Zeichenfolge möchten, mit der Maustaste, und wählen Sie **einfügen** aus dem Kontextmenü.

   > [!NOTE]
   > Wenn die **ID** oder **Wert** der verschobenen Zeichenfolge Konflikte mit vorhandenen **ID** oder **Wert** in der Zieldatei, entweder die **ID** oder **Wert** der verschobenen Zeichenfolge ändert. Wenn eine Zeichenfolge mit dem gleichen vorhanden ist **ID**, **ID** der verschobenen Zeichenfolge ändert. Wenn eine Zeichenfolge mit dem gleichen vorhanden ist **Wert**, **Wert** der verschobenen Zeichenfolge ändert.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)<br/>
[Ressourcendateien](../windows/resource-files-visual-studio.md)<br/>
[Anpassen von Fensterlayouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)