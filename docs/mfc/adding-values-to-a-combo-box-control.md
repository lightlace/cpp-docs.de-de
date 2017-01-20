---
title: "Adding Values to a Combo Box Control"
ms.custom: na
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.dialog.combo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "combo boxes [C++], Data property"
  - "controls [Visual Studio], testing values in combo boxes"
  - "combo boxes [C++], adding values"
  - "combo boxes [C++], previewing values"
  - "controls [C++], testing values in combo boxes"
  - "Data property"
  - "combo boxes [C++], testing values"
ms.assetid: 22a78f98-fada-48b3-90d8-7fa0d8e4de51
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Values to a Combo Box Control
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Solange der Dialog\-Editor geöffnet ist, können Sie einem Kombinationsfeld\-Steuerelement Werte hinzufügen.  
  
> [!TIP]
>  Es empfiehlt sich, dem Kombinationsfeld alle Werte hinzuzufügen, *bevor* seine Größe im Dialog\-Editor geändert wird. Andernfalls ist der Text, der im Kombinationsfeld angezeigt werden soll, möglicherweise abgeschnitten.  
  
#### So geben Sie Werte in ein Kombinationsfeld\-Steuerelement ein  
  
1.  Markieren Sie das Kombinationsfeld\-Steuerelement, indem Sie darauf klicken.  
  
2.  Führen Sie im [Eigenschaftenfenster](../Topic/Properties%20Window.md) einen Bildlauf zur Eigenschaft **Daten** durch.  
  
    > [!NOTE]
    >  Wenn die Eigenschaften nach Typ sortiert angezeigt werden, finden Sie **Daten** unter **Verschiedenes**.  
  
3.  Klicken Sie in den Wertebereich der Eigenschaft **Daten**, und geben Sie die Datenwerte durch Semikolons getrennt ein.  
  
    > [!NOTE]
    >  Zwischen den Werten sollten keine Leerzeichen stehen, da Leerzeichen die alphabetische Sortierung in der Dropdownliste verfälschen können.  
  
4.  Nachdem alle Werte eingegeben wurden, klicken Sie auf **Eingeben**.  
  
 Informationen dazu, wie Sie den Dropdownbereich eines Kombinationsfelds vergrößern, finden Sie unter [Festlegen der Größe des Kombinationsfelds und seiner Dropdownliste](../mfc/setting-the-size-of-the-combo-box-and-its-drop-down-list.md).  
  
> [!NOTE]
>  Win32\-Projekten können mit diesem Verfahren keine Werte hinzugefügt werden \(bei Win32\-Projekten ist die Eigenschaft **Daten** abgeblendet\).  Da Win32\-Projekte keine Bibliotheken aufweisen, die diese Funktionalität unterstützen, müssen die Werte einem Kombinationsfeld in einem Win32\-Projekt programmgesteuert hinzugefügt werden.  
  
#### So testen Sie die Darstellung von Werten in einem Kombinationsfeld  
  
1.  Klicken Sie, nachdem Sie Werte für die Eigenschaft **Daten** eingegeben haben, auf der [Symbolleiste des Dialog\-Editors](../mfc/showing-or-hiding-the-dialog-editor-toolbar.md) auf die Schaltfläche **Testen**.  
  
     Führen Sie den Bildlauf durch die gesamte Werteliste durch.  Die Werte werden genauso angezeigt, wie sie in der Eigenschaft **Daten** im Eigenschaftenfenster eingegeben wurden.  Rechtschreibung bzw. Groß\-\/Kleinschreibung werden nicht überprüft.  
  
     Drücken Sie ESC, um zum Dialog\-Editor zurückzukehren.  
  
 Informationen zum Hinzufügen von Ressourcen zu verwalteten Projekten finden Sie unter [Ressourcen in Anwendungen](../Topic/Resources%20in%20Desktop%20Apps.md) im *.NET Framework\-Entwicklerhandbuch.* Informationen zum manuellen Hinzufügen von Ressourcendateien zu verwalteten Projekten, zum Zugreifen auf Ressourcen, zum Anzeigen statischer Ressourcen und zum Zuweisen von Ressourcenzeichenfolgen zu Eigenschaften finden Sie unter [Exemplarische Vorgehensweise: Lokalisieren von Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) und [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
### Anforderungen  
 Win32  
  
## Siehe auch  
 [Controls in Dialog Boxes](../mfc/controls-in-dialog-boxes.md)   
 [Steuerelemente](../mfc/controls-mfc.md)