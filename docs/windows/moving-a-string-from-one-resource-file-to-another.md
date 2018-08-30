---
title: Verschieben von Zeichenfolgen aus einer Ressourcendatei in eine andere | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- strings [C++], moving between files
- resource script files, moving strings
- string editing, moving strings between resources
- String editor, moving strings between files
ms.assetid: 94f8ee81-9b4c-4788-ba95-68c58db38029
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbed58a02d1b9ff6db1400a677a9049d23892b40
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212874"
---
# <a name="moving-a-string-from-one-resource-file-to-another"></a>Verschieben von Zeichenfolgen zwischen Ressourcendateien

### <a name="to-move-a-string-from-one-resource-script-file-to-another"></a>Eine Zeichenfolge aus einer Ressource-Skriptdatei auf einen anderen zu verschieben.

1. Öffnen Sie die Zeichenfolgentabellen in beide RC-Dateien ein. (Weitere Informationen finden Sie unter [Anzeigen von Ressourcen eine Ressource außerhalb eines Projekts](../windows/how-to-open-a-resource-script-file-outside-of-a-project-standalone.md).)

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Mit der rechten Maustaste in der Zeichenfolge, die Sie verschieben möchten und wählen Sie **Ausschneiden** aus dem Kontextmenü.

3. Platzieren Sie den Cursor in der Ziel- **Zeichenfolgen-Editor** Fenster.

4. In der RC-Datei in das Sie verschieben, die Zeichenfolge möchten, mit der Maustaste, und wählen Sie **einfügen** aus dem Kontextmenü.

   > [!NOTE]
   > Wenn die **ID** oder **Wert** der verschobenen Zeichenfolge Konflikte mit vorhandenen **ID** oder **Wert** in der Zieldatei, entweder die **ID** oder **Wert** der verschobenen Zeichenfolge ändert. Wenn eine Zeichenfolge mit dem gleichen vorhanden ist **ID**, **ID** der verschobenen Zeichenfolge ändert. Wenn eine Zeichenfolge mit dem gleichen vorhanden ist **Wert**, **Wert** der verschobenen Zeichenfolge ändert.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)  
[Ressourcendateien](../windows/resource-files-visual-studio.md)  
[Anpassen von Fensterlayouts](/visualstudio/ide/customizing-window-layouts-in-visual-studio)  