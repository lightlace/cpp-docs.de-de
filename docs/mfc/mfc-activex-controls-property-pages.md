---
title: "MFC-ActiveX-Steuerelemente: Eigenschaftenseiten für | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dde35df301c34a6c3a29c48d5ad145681b64a72e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-property-pages"></a>MFC-ActiveX-Steuerelemente: Eigenschaftenseite
Eigenschaftenseiten können Benutzer eines ActiveX-Steuerelements anzeigen und Ändern der Eigenschaften von ActiveX-Steuerelements. Diese Eigenschaften erfolgt durch den Aufruf ein Dialogfeld der Eigenschaftenseiten für eine oder mehrere enthält, die eine benutzerdefinierte grafische Schnittstelle zum Anzeigen und bearbeiten die Eigenschaften des Steuerelements bereitstellen.  
  
 ActiveX-Steuerelement-Eigenschaftenseiten werden auf zwei Arten angezeigt:  
  
-   Wenn das Steuerelement Eigenschaftenverb (**OLEIVERB_PROPERTIES**) wird aufgerufen, das Steuerelement öffnet ein modales Dialogfeld, die Eigenschaftenseiten für das Steuerelement enthält.  
  
-   Der Container kann ein eigenen nicht modales Dialogfeld angezeigt, das die Eigenschaftenseiten des ausgewählten Steuerelements anzeigt.  
  
 Das Dialogfeld "Eigenschaften" (in der folgenden Abbildung dargestellt) besteht aus einen Bereich für die Anzeige der aktuellen Eigenschaftenseite der Registerkarten für den Wechsel zwischen Eigenschaftenseiten und eine Auflistung von Schaltflächen, die Ausführung allgemeiner Aufgaben wie das Schließen des Eigenschaftendialogfelds für die Seite ", Abbrechen von Änderungen oder sofortiges Anwenden von Änderungen auf das ActiveX-Steuerelement.  
  
 ![Eigenschaftendialogfeld für Circ3](../mfc/media/vc373i1.gif "vc373i1")  
Eigenschaften (Dialogfeld)  
  
 In diesem Artikel werden Themen zum Verwenden von Eigenschaftenseiten in einem ActiveX-Steuerelement behandelt. Dazu gehören:  
  
-   [Implementieren die Standardseite für die Eigenschaft für ein ActiveX-Steuerelement](#_core_implementing_the_default_property_page)  
  
-   [Hinzufügen von Steuerelementen zu einer Eigenschaftenseite](#_core_adding_controls_to_a_property_page)  
  
-   [Anpassen der DoDataExchange-Funktion](#_core_customizing_the_dodataexchange_function)  
  
 Weitere Informationen zum Verwenden von Eigenschaftenseiten in einem ActiveX-Steuerelement finden Sie unter den folgenden Artikeln:  
  
-   [MFC-ActiveX-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)  
  
-   [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)  
  
 Weitere Informationen zum Verwenden von Eigenschaftenseiten in einer MFC_Anwendung als ein ActiveX-Steuerelement, finden Sie unter [Eigenschaftenblätter](../mfc/property-sheets-mfc.md).  
  
##  <a name="_core_implementing_the_default_property_page"></a>Implementieren die Standard-Eigenschaftenseite  
 Wenn Sie den ActiveX-Steuerelement-Assistenten verwenden, auf dem Steuerelementprojekt erstellen, enthält das ActiveX-Steuerelement-Assistent eine Standard-Eigenschaftenklasse von Seite für das Steuerelement abgeleitet [COlePropertyPage Klasse](../mfc/reference/colepropertypage-class.md). Zu Beginn dieser Eigenschaftenseite ist leer, aber Sie können alle Dialogfeld-Steuerelement oder eine Gruppe von Steuerelementen, hinzufügen. Da ActiveX-Steuerelement-Assistent standardmäßig eine zusätzliche Eigenschaft Seitenklassen nur eine Eigenschaft Page-Klasse erstellt (auch abgeleitet `COlePropertyPage`) muss mit der Klassenansicht erstellt werden. Weitere Informationen zu diesem Verfahren finden Sie unter [MFC-ActiveX-Steuerelemente: Hinzufügen von einem anderen benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md).  
  
 Implementieren eine Eigenschaft Seite (in diesem Fall ist die Standardeinstellung) ist eine dreistufige Prozess:  
  
#### <a name="to-implement-a-property-page"></a>Zum Implementieren einer Eigenschaftenseite  
  
1.  Hinzufügen einer `COlePropertyPage`-Klasse abgeleitet, auf dem Steuerelementprojekt. Wenn das Projekt mit dem ActiveX-Steuerelement-Assistenten (wie in diesem Fall) erstellt wurde, ist die Standardklasse für Eigenschaftenseiten bereits vorhanden.  
  
2.  Verwenden des Dialog-Editors hinzufügen der Steuerelemente auf der Seite eigenschaftsvorlage.  
  
3.  Anpassen der `DoDataExchange` Funktion der `COlePropertyPage`-abgeleitete Klasse zum Austauschen von Werten zwischen dem Eigenschaftenseiten-Steuerelement und das ActiveX-Steuerelement.  
  
 Zwecke verwenden, die folgenden Verfahren verwenden Sie beispielsweise ein einfaches Steuerelement (mit dem Namen "Sample"). Beispiel mit dem ActiveX-Steuerelement-Assistenten erstellt wurde, und enthält nur die vordefinierte Caption-Eigenschaft.  
  
##  <a name="_core_adding_controls_to_a_property_page"></a>Hinzufügen von Steuerelementen zu einer Eigenschaftenseite  
  
#### <a name="to-add-controls-to-a-property-page"></a>Zum Hinzufügen von Steuerelementen auf einer Eigenschaftenseite  
  
1.  Öffnen Sie mit dem Steuerelementprojekt öffnen die Ressourcenansicht.  
  
2.  Doppelklicken Sie auf die **Dialogfeld** Symbol "Directory".  
  
3.  Öffnen der **IDD_PROPPAGE_SAMPLE** (Dialogfeld).  
  
     Die ActiveX-Steuerelement-Assistent fügt den Namen des Projekts an das Ende der Dialogfeld-ID, in diesem Beispiel.  
  
4.  Ziehen Sie das ausgewählte Steuerelement aus der Toolbox auf das Dialogfeld im Feld Bereich.  
  
5.  In diesem Beispiel ein Text label-Steuerelement "Beschriftung:" und ein Bearbeitungsfeld-Steuerelement mit einer **IDC_CAPTION** Bezeichner sind ausreichend.  
  
6.  Klicken Sie auf **speichern** auf der Symbolleiste, um die Änderungen zu speichern.  
  
 Die Benutzeroberfläche geändert wurde, müssen Sie im Bearbeitungsfeld mit der Caption-Eigenschaft zu verknüpfen. Dies erfolgt im folgenden Abschnitt durch Bearbeiten der `CSamplePropPage::DoDataExchange` Funktion.  
  
##  <a name="_core_customizing_the_dodataexchange_function"></a>Anpassen der DoDataExchange-Funktion  
 Die Eigenschaftenseite [Ddx_managedcontrol](../mfc/reference/cwnd-class.md#dodataexchange) -Funktion können Sie Eigenschaftswerte über die Seite mit den tatsächlichen Werten der Eigenschaften im Steuerelement zu verknüpfen. Um Verbindungen herzustellen, müssen Sie die entsprechende Seite Eigenschaftenfelder ihre entsprechenden Steuerelementeigenschaften zuordnen.  
  
 Diese Zuordnungen werden mithilfe der Eigenschaftenseite implementiert **DDP_** Funktionen. Die **DDP_** Funktionen funktionieren, wie die **DDX_** Funktionen, die in MFC-Standarddialogfelder mit einer Ausnahme verwendet. Zusätzlich zu den Verweis auf eine Membervariable **DDP_** Funktionen den Namen der Steuerelementeigenschaft annehmen. Im folgenden finden Sie eine typische Eintrag in der `DoDataExchange` -Funktion für eine Eigenschaftenseite.  
  
 [!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]  
  
 Diese Funktion ordnet der Eigenschaftenseite `m_caption` Membervariable mit der Beschriftung mithilfe der `DDP_TEXT` Funktion.  
  
 Nachdem Sie die Eigenschaftenseiten-Steuerelement eingefügt haben, müssen Sie eine Verknüpfung zwischen den Steuerelementen für die Eigenschaft einrichten `IDC_CAPTION`, und verwenden Sie die tatsächliche Steuerelementeigenschaft Beschriftung, die **DDP_Text** funktionieren wie oben beschrieben.  
  
 [Eigenschaftenseiten](../mfc/reference/property-pages-mfc.md) stehen für andere Dialogfeld-Steuerelementtypen, z. B. Kontrollkästchen, Optionsfelder, und Listenfelder. Die folgende Tabelle enthält den gesamten Satz von Eigenschaftenseite **DDP_** Funktionen und ihre Zwecke zu verwenden:  
  
### <a name="property-page-functions"></a>Seite "-Eigenschaftenfunktionen  
  
|Funktionsname|Mit dieser Funktion können verknüpfen|  
|-------------------|-------------------------------|  
|`DDP_CBIndex`|Die ausgewählte Zeichenfolge Index in einem Kombinationsfeld mit einer Steuerelementeigenschaft.|  
|`DDP_CBString`|Die markierte Zeichenfolge aus einem Kombinationsfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge dieselben Buchstaben als Wert der Eigenschaft kann beginnen, darf jedoch muss nicht vollständig damit übereinstimmen.|  
|`DDP_CBStringExact`|Die markierte Zeichenfolge aus einem Kombinationsfeld mit einer Steuerelementeigenschaft. Der markierten Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|  
|`DDP_Check`|Ein Kontrollkästchen mit einer Steuerelementeigenschaft.|  
|`DDP_LBIndex`|Die ausgewählte Zeichenfolge Index in einem Listenfeld mit einer Steuerelementeigenschaft.|  
|`DDP_LBString`|Die ausgewählte Zeichenfolge in einem Listenfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge dieselben Buchstaben als Wert der Eigenschaft kann beginnen, darf jedoch muss nicht vollständig damit übereinstimmen.|  
|`DDP_LBStringExact`|Die ausgewählte Zeichenfolge in einem Listenfeld mit einer Steuerelementeigenschaft. Der markierten Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|  
|`DDP_Radio`|Ein Optionsfeld mit einer Steuerelementeigenschaft.|  
|**DDP_Text**|Text mit einer Steuerelementeigenschaft.|  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [COlePropertyPage-Klasse](../mfc/reference/colepropertypage-class.md)
