---
title: Hinzufügen von Formatierung oder Sonderzeichen auf eine Zeichenfolgenressource (C++) | Microsoft-Dokumentation
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
ms.openlocfilehash: 328db31cf595247932a17a96dab6c6395813470c
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49082409"
---
# <a name="adding-formatting-or-special-characters-to-a-string-resource-c"></a>Hinzufügen von Formatierung oder Sonderzeichen auf eine Zeichenfolgenressource (C++)

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

Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten (diejenigen, die die common Language Runtime), finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *(.NET Framework Developer's Guide*. Weitere Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](/previous-versions/visualstudio/visual-studio-2010/y99d1cd3).

## <a name="requirements"></a>Anforderungen

Win32

## <a name="see-also"></a>Siehe auch

[Zeichenfolgen-Editor](../windows/string-editor.md)  