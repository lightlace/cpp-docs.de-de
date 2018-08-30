---
title: Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolge | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- special characters, adding to strings
- ASCII characters, adding to strings
- strings [C++], formatting
- strings [C++], special characters
ms.assetid: c40f394a-8b2c-4896-ab30-6922863ddbb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1b4eda998d598e70fd687276a2d2941d224da4d7
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211677"
---
# <a name="adding-formatting-or-special-characters-to-a-string"></a>Hinzufügen von Formatierung oder Sonderzeichen zu einer Zeichenfolge

### <a name="to-add-formatting-or-special-characters-to-a-string"></a>Um eine Zeichenfolge formatierungs-oder Sonderzeichen hinzufügen

1. Öffnen Sie durch Doppelklicken auf das Symbol in der Zeichenfolgentabelle [Ressourcenansicht](../windows/resource-view-window.md).

   > [!NOTE]
   > Wenn das Projekt noch keine RC-Datei enthält, informieren Sie sich unter [Erstellen einer neuen Ressourcenskriptdatei](../windows/how-to-create-a-resource-script-file.md).

2. Wählen Sie die Zeichenfolge, die Sie ändern möchten.

3. In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), fügen Sie eine der standardmäßigen Escape-Sequenzen auf den Text im unten aufgeführten der **Beschriftung** Feld, und drücken Sie **EINGABETASTE**.

   |Um dies zu erhalten.|Geben Sie Folgendes|
   |-----------------|---------------|
   |Zeilenwechsel|\n|
   |Wagenrücklauf|\r|
   |Registerkarte|\t|
   |Umgekehrter Schrägstrich (\\)|\\\|
   |ASCII-Zeichen|\ddd (oktale)|
   |Warnung (Glocke)|\a|

> [!NOTE]
> Die **Zeichenfolge** -Editor unterstützt nicht den vollständigen Satz von ASCII-Zeichen in Escapezeichen. Sie können nur die oben aufgeführten verwenden.

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3\(v=vs.100\)).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)  