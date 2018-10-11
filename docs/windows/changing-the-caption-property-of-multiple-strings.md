---
title: Ändern die Caption-Eigenschaft von mehreren Zeichenfolgenressourcen (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- String editor [C++], changing properties of multiple strings
- string tables [C++], changing caption of multiple strings
ms.assetid: 82ac4389-fd9c-4794-a18f-c6bf5b253bd7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fe08462c95750f483cdec5650fccb1c199505ee1
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082396"
---
# <a name="changing-the-caption-property-of-multiple-string-resources-c"></a>Ändern die Caption-Eigenschaft von mehreren Zeichenfolgenressourcen (C++)

Das folgende Verfahren erfahren Sie, wie Sie die Eigenschaft "Beschriftung" mehrerer Zeichenfolgen ändern.

### <a name="to-change-the-caption-property-of-multiple-strings"></a>So ändern Sie die Eigenschaft "Beschriftung" mehrerer Zeichenfolgen

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie die Zeichenfolgen, die Sie ändern, indem Sie sie gedrückt halten, möchten die **STRG** gedrückt, während Sie die einzelnen Elemente klicken.

3. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), geben Sie einen neuen Wert für die Eigenschaft, die Sie ändern möchten.

4. Drücken Sie die **EINGABETASTE**.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)  