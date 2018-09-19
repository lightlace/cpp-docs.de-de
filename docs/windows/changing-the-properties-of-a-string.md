---
title: Ändern der Eigenschaften einer Zeichenfolgenressource (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- resource identifiers, string properties
- string tables [C++], changing strings
- strings [C++], properties
ms.assetid: 0a220434-f444-4405-9a64-d28d6b965687
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b1fdf47a6995a29641cf18018199f8d7b88a622c
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318355"
---
# <a name="changing-the-properties-of-a-string-resource-c"></a>Ändern der Eigenschaften einer Zeichenfolgenressource (C++)

### <a name="to-change-a-string-or-its-identifier"></a>Eine Zeichenfolge oder den Bezeichner ändern.

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie die Zeichenfolge, die Sie bearbeiten möchten, und doppelklicken Sie auf die **ID**, **Wert**, oder **Beschriftung** Spalte. Sie können jetzt:

   - Wählen Sie eine **ID** aus der **ID Dropdown-** Liste oder Eingabe ein `ID` direkt an Ort.

   - Geben Sie eine andere Zahl in die **Wert** Spalte.

   - Geben Sie die Änderungen in der **Beschriftung** Spalte.

        > [!NOTE]
        >  Sie können auch die Eigenschaften einer Zeichenfolge im Bearbeiten der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window).

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)  