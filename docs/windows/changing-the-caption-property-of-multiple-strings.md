---
title: Die Eigenschaft "Beschriftung" mehrerer Zeichenfolgen ändern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor, changing properties of multiple strings
- strings [C++], changing caption property of multiple
- string editing, string tables
- string tables, changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 205fbd0674fa1a64ee6aeb66edfecdc1861ccba7
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42578371"
---
# <a name="changing-the-caption-property-of-multiple-strings"></a>Ändern der Eigenschaft "Beschriftung" mehrerer Zeichenfolgen

Das folgende Verfahren erfahren Sie, wie Sie die Eigenschaft "Beschriftung" mehrerer Zeichenfolgen ändern.

### <a name="to-change-the-caption-property-of-multiple-strings"></a>So ändern Sie die Eigenschaft "Beschriftung" mehrerer Zeichenfolgen

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie die Zeichenfolgen, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie die einzelnen Elemente klicken.

3. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie einen neuen Wert für die Eigenschaft, die Sie ändern möchten.

4. Drücken Sie die **EINGABETASTE**.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](http://msdn.microsoft.com/9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Exemplarische Vorgehensweise: Verwenden von Ressourcen für die Lokalisierung mit ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)  