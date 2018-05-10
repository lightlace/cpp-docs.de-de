---
title: Definieren von Membervariablen für Dialogfeld-Steuerelemente | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- member variables, defining for controls
- variables, dialog box control member variables
- controls [C++], member variables
- Dialog editor, defining member variables for controls
ms.assetid: 84347c63-c33c-4b04-91f5-6d008c45ba58
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8ba8fc95290ecb90557203be2b6ab4cce18b91e3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="defining-member-variables-for-dialog-controls"></a>Definieren von Membervariablen für Dialogfeld-Steuerelemente
Mit der folgenden Methode können Sie eine Membervariable für beliebige Dialogfenster-Steuerelemente außer Schaltflächen definieren.  
  
> [!NOTE]
>  Dieser Artikel gilt nur für Dialogfeld-Steuerelemente innerhalb eines MFC-Projekts. ATL-Projekte verwenden, sollten die **neue Windows-Meldungen und Ereignishandler** (Dialogfeld).  
  
### <a name="to-define-a-member-variable-for-a-non-button-dialog-box-control"></a>So definieren Sie eine Membervariable für ein Dialogfeld-Steuerelement (kein Schaltflächen-Steuerelement)  
  
1.  In der [Dialog-Editor](../windows/dialog-editor.md), wählen Sie ein Steuerelement.  
  
2.  Beim Drücken der **STRG** Schlüssel, doppelklicken Sie auf das Dialogfeld-Steuerelement.  
  
     Die [Assistenten zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) angezeigt wird.  
  
3.  Geben Sie die entsprechende Informationen in den **Hinzufügen von Membervariablen** Assistenten. Weitere Informationen finden Sie unter [Dialogdatenaustausch](../mfc/dialog-data-exchange.md).  
  
4.  Klicken Sie auf **OK** um zum Dialog-Editor zurückzukehren.  
  
    > [!TIP]
    >  Doppelklicken Sie auf das Steuerelement, um von einem Dialogfeld-Steuerelement zu seinem vorhandenen Handler zu wechseln.  
  

  
 Sie können auch die **Membervariablen** Registerkarte **MFC-Klassen-Assistent** neue Membervariablen für eine angegebene Klasse hinzufügen und anzeigen, die bereits definiert wurden.  
  
 Anforderungen  
  
 MFC  
  
## <a name="see-also"></a>Siehe auch  
 [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md)   
 [Hinzufügen neuer Funktionen mit Code-Assistenten](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [MFC-Klassen-Assistent](../mfc/reference/mfc-class-wizard.md)   
 [Hinzufügen einer Klasse](../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC-Meldungshandler](../mfc/reference/adding-an-mfc-message-handler.md)

