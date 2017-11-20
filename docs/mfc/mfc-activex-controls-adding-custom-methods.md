---
title: "MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], methods
- PtInCircle custom method [MFC]
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ead8411d22539218c18d21b8af7d020cc267879f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="mfc-activex-controls-adding-custom-methods"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden
Benutzerdefinierte Methoden unterscheiden sich von vordefinierten Methoden, da sie nicht bereits durch implementiert sind `COleControl`. Sie müssen die Implementierung für jede benutzerdefinierte Methode angeben, die Sie das Steuerelement hinzufügen.  
  
 Ein ActiveX-Steuerelement-Benutzer kann eine benutzerdefinierte Methode zu einem beliebigen Zeitpunkt für das Steuerelement spezifische Aktionen aufrufen. Der Eintrag in der Dispatchzuordnung für benutzerdefinierte Methoden besitzt das Format `DISP_FUNCTION`.  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a>Hinzufügen einer benutzerdefinierten Methode mit der Methode Assistent zum Hinzufügen von  
 Das folgende Verfahren veranschaulicht die benutzerdefinierte-Methode PtInCircle Codegerüst für ein ActiveX-Steuerelement hinzufügen. PtInCircle bestimmt, ob die Koordinaten für das Steuerelement übergeben innerhalb oder außerhalb des Kreises. Dasselbe Verfahren kann auch verwendet werden, andere benutzerdefinierte Methoden hinzugefügt. Ersetzen Sie durch Ihre benutzerdefinierten Methodennamen und seine Parameter für die PtInCircle Methodennamen und Parameter.  
  
> [!NOTE]
>  Dieses Beispiel verwendet die `InCircle` Funktion aus dem Artikel Ereignisse. Weitere Informationen zu dieser Funktion finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Hinzufügen benutzerdefinierter Ereignisse ein ActiveX-Steuerelement](../mfc/mfc-activex-controls-adding-custom-events.md).  
  
#### <a name="to-add-the-ptincircle-custom-method-using-the-add-method-wizard"></a>Die benutzerdefinierte PtInCircle-Methode, die mithilfe des Assistenten zum Hinzufügen einer Methode hinzufügen  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Methode hinzufügen**.  
  
     Dies öffnet den Assistenten zum Hinzufügen einer Methode.  
  
5.  In der **Methodennamen** geben `PtInCircle`.  
  
6.  In der **Internnamen** Feld, geben Sie den Namen der internen Funktion der Methode oder den Standardwert (in diesem Fall `PtInCircle`).  
  
7.  In der **Rückgabetyp** auf **VARIANT_BOOL** für den Rückgabetyp der Methode.  
  
8.  Mithilfe der **Parametertyp** und **Parametername** Steuerelemente hinzufügen, einen Parameter namens `xCoord` (Typ **OLE_XPOS_PIXELS**).  
  
9. Mithilfe der **Parametertyp** und **Parametername** Steuerelemente hinzufügen, einen Parameter namens `yCoord` (Typ **OLE_YPOS_PIXELS**).  
  
10. Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a>Hinzufügen von Assistenten Änderungen für benutzerdefinierte Methoden  
 Wenn Sie eine benutzerdefinierte Methode hinzufügen, werden den Assistenten zum Hinzufügen einer Methode einige Änderungen an dem Control-Klasse-Header (. H) und die Implementierung (. CPP)-Dateien. Die Dispatch-Map-Deklaration im Header Control-Klasse die folgende Zeile hinzugefügt (. H)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#18](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_1.h)]  
  
 Dieser Code deklariert einen Dispatch-Methode Ereignishandler mit dem Namen `PtInCircle`. Diese Funktion kann vom Benutzer Steuerelements, die mit den externen Namen PtInCircle aufgerufen werden.  
  
 Die folgende Zeile wird an des Steuerelements hinzugefügt. IDL-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#19](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_2.idl)]  
  
 Diese Zeile weist der PtInCircle-Methode eine bestimmte ID-Nummer der Position der Methode in der Liste Assistenten zum Hinzufügen von Methoden, Eigenschaften und Methoden. Da den Assistenten zum Hinzufügen einer Methode für die benutzerdefinierte Methode hinzufügen verwendet wurde, wurde der Eintrag für sie des Projekts automatisch hinzugefügt. IDL-Datei.  
  
 Darüber hinaus die folgende Zeile befindet, in der Implementierung (. CPP)-Datei der Steuerelementklasse wird Dispatchzuordnung des Steuerelements hinzugefügt:  
  
 [!code-cpp[NVC_MFC_AxUI#20](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_3.cpp)]  
  
 Die `DISP_FUNCTION` Makro ordnet die Methode PtInCircle Handlerfunktion des Steuerelements, `PtInCircle`, deklariert den Rückgabetyp zu sein **VARIANT_BOOL**, und es werden zwei Parametern vom Typ deklariert **VTS_XPOS_PIXELS** und **VTS_YPOSPIXELS** übergeben werden `PtInCircle`.  
  
 Schließlich fügt den Assistenten zum Hinzufügen einer Methode die Stub-Funktion `CSampleCtrl::PtInCircle` an das Ende der Implementierung des Steuerelements (. CPP)-Datei. Für `PtInCircle` funktionieren wie zuvor erwähnt, müssen sie wie folgt geändert werden:  
  
 [!code-cpp[NVC_MFC_AxUI#21](../mfc/codesnippet/cpp/mfc-activex-controls-adding-custom-methods_4.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Symbole in der Klassenansicht und im Objektbrowser](/visualstudio/ide/class-view-and-object-browser-icons)

