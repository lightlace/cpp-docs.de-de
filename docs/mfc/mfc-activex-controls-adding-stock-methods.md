---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2005391c6d91ee09703194eb8b8062ecfe08ba77
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36929798"
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Methoden
Eine vordefinierte Methode unterscheidet sich von einer benutzerdefinierten Methode, da er bereits von der Klasse implementiert wird [COleControl](../mfc/reference/colecontrol-class.md). Beispielsweise `COleControl` enthält eine vordefinierte Memberfunktion, die die Aktualisierungsmethode für das Steuerelement unterstützt. Die Dispatch-Eintrag für die Zuordnung für diese vordefinierten Methode lautet DISP_STOCKFUNC_REFRESH.  
  
 `COleControl` unterstützt zwei vordefinierte Methoden: DoClick und aktualisieren. Aktualisierung wird aufgerufen, vom Benutzer des Steuerelements, um die Darstellung des Steuerelements sofort zu aktualisieren. DoClick wird aufgerufen, um auf das Steuerelement ausgelöst Ereignis.  
  
|Methode|Dispatch-Zuordnungseintrag|Kommentar|  
|------------|------------------------|-------------|  
|`DoClick`|**DISP_STOCKPROP_DOCLICK)**|Wird ausgelöst Click-Ereignis aus.|  
|`Refresh`|**DISP_STOCKPROP_REFRESH)**|Sofort aktualisiert die Darstellung des Steuerelements.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a> Hinzufügen einer vordefinierten Methode mithilfe der Methode Assistent zum Hinzufügen von  
 Hinzufügen einer vordefinierten Methode ist einfach mithilfe der [Assistenten zum Hinzufügen von Methoden](../ide/add-method-wizard.md). Das folgende Verfahren veranschaulicht das Hinzufügen von die Aktualisierungsmethode an ein Steuerelement mit dem MFC-ActiveX-Steuerelement-Assistenten erstellt.  
  
#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Die vordefinierte Aktualisierungsmethode mithilfe des Assistenten zum Hinzufügen einer Methode hinzufügen  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Methode hinzufügen**.  
  
     Dies öffnet den Assistenten zum Hinzufügen einer Methode.  
  
5.  In der **Methodennamen** auf **aktualisieren**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a> Hinzufügen von Assistenten Änderungen für vordefinierten Methoden  
 Da die vordefinierte Aktualisierungsmethode von Basisklasse des Steuerelements unterstützt wird die **Assistenten zum Hinzufügen von Methoden** ändert sich nicht auf die Klassendeklaration in keiner Weise das Steuerelement. Es fügt einen Eintrag für die Methode, um das Steuerelement Dispatchzuordnung und zu dessen. IDL-Datei. Das Steuerelement Dispatchzuordnung in seiner Implementierung ist die folgende Zeile hinzugefügt (. CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 Dies stellt die Aktualisierungsmethode für Benutzer des Steuerelements zur Verfügung.  
  
 Die folgende Zeile wird an des Steuerelements hinzugefügt. IDL-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 Diese Zeile weist der Aktualisierungsmethode eine bestimmte ID-Nummer.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

