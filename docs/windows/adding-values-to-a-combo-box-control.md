---
title: Hinzufügen von Werten zu einem Kombinationsfeld-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.dialog.combo
dev_langs:
- C++
helpviewer_keywords:
- combo boxes [C++], Data property
- controls [Visual Studio], testing values in combo boxes
- combo boxes [C++], adding values
- combo boxes [C++], previewing values
- controls [C++], testing values in combo boxes
- Data property
- combo boxes [C++], testing values
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c81e40de56970571ad78ceea86084b7ff7b82227
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="adding-values-to-a-combo-box-control"></a>Hinzufügen von Werten zu einem Kombinationsfeld-Steuerelement
Sie können Werte an ein Kombinationsfeld-Steuerelement hinzufügen, solange Sie den Dialog-Editor öffnen verfügen.  
  
> [!TIP]
>  Es ist ratsam, die alle Werte im Kombinationsfeld hinzufügen *vor* Sie seine Größe im Dialog-Editor, oder Sie möglicherweise abgeschnitten, Text, der im Kombinationsfeld-Steuerelement angezeigt werden soll.  
  
#### <a name="to-enter-values-into-a-combo-box-control"></a>Eingeben von Werten in einem Kombinationsfeld-Steuerelement  
  
1.  Wählen Sie das Kombinationsfeld-Steuerelement, indem Sie darauf klicken.  
  
2.  In der [Fenster "Eigenschaften"](/visualstudio/ide/reference/properties-window), führen Sie einen Bildlauf nach unten, um die **Daten** Eigenschaft.  
  
    > [!NOTE]
    >  Wenn Sie Eigenschaften gruppiert nach Typ anzeigen **Daten** wird angezeigt, der **Verschiedenes** Eigenschaften.  
  
3.  Klicken Sie auf im Bereich "Wert" für die **Daten** Eigenschaft, und geben die Datenwerte, die durch Semikolons getrennt sind.  
  
    > [!NOTE]
    >  Leerzeichen zwischen den Werten kann nicht abgelegt werden, da Leerzeichen in der Dropdown Liste verfälschen beeinträchtigen.  
  
4.  Klicken Sie auf **EINGABETASTE** Sie abschließend Werte hinzufügen.  
  
 Informationen zum Vergrößern der Dropdownteil des Kombinationsfelds, finden Sie unter [Festlegen der Größe des Kombinationsfelds und seiner Dropdownliste](setting-the-size-of-the-combo-box-and-its-drop-down-list.md).  
  
> [!NOTE]
>  Win32-Projekte, die mit dieser Prozedur können keine Werte hinzugefügt (der **Daten** Eigenschaft ist für Win32-Projekte abgeblendet). Da Win32-Projekte keine Bibliotheken, die diese Funktion hinzuzufügen, müssen Sie Werte in ein Kombinationsfeld mit einem Win32-Projekt programmgesteuert hinzufügen.  
  
#### <a name="to-test-the-appearance-of-values-in-a-combo-box"></a>So testen Sie die Darstellung der Werte in einem Kombinationsfeld  
  
1.  Nach dem Eingeben von Werten in der **Daten** -Eigenschaft, klicken Sie auf die **Test** Schaltfläche auf der [Dialog-Editor-Symbolleiste](../windows/showing-or-hiding-the-dialog-editor-toolbar.md).  
  
     Wiederholen Sie dann einen Bildlauf nach unten der gesamte Werteliste. Werte werden angezeigt, genau so, wie sie in typisiert sind die **Daten** Eigenschaft im Eigenschaftenfenster angezeigt. Es gibt keine Rechtschreib- oder Großschreibung zu überprüfen.  
  
     Drücken Sie ESC, um zum Dialogfeld-Editor zurückzukehren.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Desktop-Apps](/dotnet/framework/resources/index) in die *.NET Framework-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, den Zugriff auf Ressourcen, zum Anzeigen statischer Ressourcen und Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften, finden Sie unter [Erstellen von Ressourcendateien für Desktop-Apps](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Informationen zur Globalisierung und Lokalisierung von Ressourcen in verwalteten apps finden Sie unter [Globalizing und Lokalisieren von .NET Framework-Anwendungen](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Anforderungen  
 Win32  
  
## <a name="see-also"></a>Siehe auch  
 [Steuerelemente in Dialogfeldern](../windows/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

