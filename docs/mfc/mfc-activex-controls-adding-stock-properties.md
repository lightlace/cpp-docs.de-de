---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BackColor property [MFC]
- properties [MFC], adding stock
- ForeColor property [MFC]
- MFC ActiveX controls [MFC], properties
- foreground colors, ActiveX controls
- foreground colors [MFC]
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 791694bfa1bcd7472be4691d9aef133b80ccace4
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/25/2018
ms.locfileid: "36930129"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften
Basiseigenschaften unterscheiden sich von benutzerdefinierten Eigenschaften, insofern, dass sie bereits von der Klasse implementiert sind `COleControl`. `COleControl` enthält vordefinierte Memberfunktionen, die allgemeine Eigenschaften für das Steuerelement zu unterstützen. Einige allgemeinen Eigenschaften enthalten die Beschriftung des Steuerelements und die Farben für Vordergrund und Hintergrund. Informationen über weitere vordefinierten Eigenschaften finden Sie unter [Stock Eigenschaften unterstützt, indem Sie den Assistenten zum Hinzufügen einer Eigenschaft](#_core_stock_properties_supported_by_classwizard) weiter unten in diesem Artikel. Die Dispatch-Zuordnungseinträge für vordefinierte Eigenschaften immer DISP_STOCKPROP vorangestellt.  
  
 In diesem Artikel wird beschrieben, wie eine Systemeigenschaft (in diesem Fall Beschriftung) ein ActiveX-Steuerelement mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzufügen und die resultierende codeänderungen erläutert. Folgende Themen werden behandelt:  
  
-   [Verwenden den Assistenten zum Hinzufügen einer Eigenschaft zum Hinzufügen von einer Systemeigenschaft](#_core_using_classwizard_to_add_a_stock_property)  
  
-   [Fügen Sie der Assistent zum Eigenschaften Änderungen für Basiseigenschaften](#_core_classwizard_changes_for_stock_properties)  
  
-   [Basiseigenschaften, die unterstützt werden, indem Sie den Assistenten zum Hinzufügen einer Eigenschaft](#_core_stock_properties_supported_by_classwizard)  
  
-   [Vordefinierte Eigenschaften und Benachrichtigung](#_core_stock_properties_and_notification)  
  
-   [Farbe-Eigenschaften](#_core_color_properties)  
  
    > [!NOTE]
    >  Benutzerdefinierte Steuerelemente in Visual Basic verfügen in der Regel Eigenschaften wie oben, links, Breite, Höhe, ausrichten, Tag, Name, TabIndex, TabStop und übergeordneten. ActiveX-Steuerelementcontainer, allerdings sind verantwortlich für die Implementierung dieser Steuerelementeigenschaften und ActiveX-Steuerelemente sollten daher nicht unterstützen diese Eigenschaften.  
  
##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> Mithilfe der Eigenschaft Assistenten zum Hinzufügen einer vordefinierten Eigenschaft hinzufügen  
 Hinzufügen von vordefinierten Eigenschaften erfordert weniger Code als benutzerdefinierte Eigenschaften hinzufügen, da Unterstützung für die Eigenschaft automatisch von etlfilereadevent `COleControl`. Das folgende Verfahren veranschaulicht das Hinzufügen von Aktie Caption-Eigenschaft für ein ActiveX-Steuerelement-Framework und kann auch zum Hinzufügen von anderen Basiseigenschaften verwendet werden. Ersetzen Sie den Namen der ausgewählten Systemeigenschaft für Beschriftung an.  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Hinzufügen von vordefinierten Caption-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Daraufhin wird die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  In der **Eigenschaftsname** auf **Beschriftung**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_stock_properties"></a> Hinzufügen von Eigenschaftenänderungen-Assistenten für Basiseigenschaften  
 Da `COleControl` unterstützt Basiseigenschaften, den Assistenten zum Hinzufügen einer Eigenschaft ändert sich nicht auf die Klassendeklaration in keiner Weise; die Dispatchzuordnung die Eigenschaft hinzugefügt. Der Assistent zum Hinzufügen von Eigenschaften der Dispatchzuordnung des Steuerelements in der Implementierung befindet sich die folgende Zeile hinzugefügt (. CPP)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]  
  
 Schnittstellenbeschreibung des Steuerelements die folgende Zeile hinzugefügt wird (. IDL)-Datei:  
  
 [!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]  
  
 Diese Zeile weist der Caption-Eigenschaft eine bestimmte ID. Beachten Sie, dass die Eigenschaft gebunden und wird eine Berechtigung aus der Datenbank vor dem Ändern des Werts anfordern.  
  
 Dadurch wird das Caption-Eigenschaft für Benutzer des Steuerelements verfügbar. Um den Wert einer vordefinierten Eigenschaft verwenden, Zugriff auf eine Membervariable oder eine Memberfunktion der `COleControl` Basisklasse. Weitere Informationen zu diesen Membervariablen und Memberfunktionen finden Sie im nächsten Abschnitt Stock Eigenschaften unterstützt, indem Sie den Assistenten zum Hinzufügen einer Eigenschaft.  
  
##  <a name="_core_stock_properties_supported_by_classwizard"></a> Vordefinierte Eigenschaften unterstützt, indem Sie die Eigenschaft Assistent zum Hinzufügen von  
 Die `COleControl` -Klasse stellt neun Basiseigenschaften bereit. Sie können die Eigenschaften hinzufügen, die mithilfe des Assistenten zum Hinzufügen einer Eigenschaft werden sollen.  
  
|Eigenschaft|Dispatch-Zuordnungseintrag|Wie Zugriffswert|  
|--------------|------------------------|-------------------------|  
|`Appearance`|DISP_STOCKPROP_APPEARANCE)|Als Wert `m_sAppearance`.|  
|`BackColor`|DISP_STOCKPROP_BACKCOLOR)|Wert zugegriffen werden kann, durch den Aufruf `GetBackColor`.|  
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE)|Als Wert `m_sBorderStyle`.|  
|`Caption`|DISP_STOCKPROP_CAPTION)|Wert zugegriffen werden kann, durch den Aufruf `InternalGetText`.|  
|`Enabled`|DISP_STOCKPROP_ENABLED)|Als Wert `m_bEnabled`.|  
|`Font`|DISP_STOCKPROP_FONT)|Finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten](../mfc/mfc-activex-controls-using-fonts.md) für die Verwendung.|  
|`ForeColor`|DISP_STOCKPROP_FORECOLOR)|Wert zugegriffen werden kann, durch den Aufruf `GetForeColor`.|  
|`hWnd`|DISP_STOCKPROP_HWND)|Als Wert `m_hWnd`.|  
|`Text`|DISP_STOCKPROP_TEXT)|Wert zugegriffen werden kann, durch den Aufruf `InternalGetText`. Diese Eigenschaft ist identisch mit `Caption`, mit Ausnahme der Eigenschaftenname.|  
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|Als Wert `m_lReadyState` oder `GetReadyState`|  
  
##  <a name="_core_stock_properties_and_notification"></a> Vordefinierte Eigenschaften und Benachrichtigung  
 Die meisten Basiseigenschaften haben Benachrichtigungsfunktionen, die überschrieben werden können. Z. B. immer dann, wenn die `BackColor` Eigenschaft geändert wird, die `OnBackColorChanged` Funktion (eine Memberfunktion der Steuerelementklasse) aufgerufen wird. Die standardmäßige Implementierung (in `COleControl`) Aufrufe `InvalidateControl`. Überschreiben Sie diese Funktion, wenn Sie zusätzliche Aktionen als Reaktion auf diese Situation möchten.  
  
##  <a name="_core_color_properties"></a> Farbe-Eigenschaften  
 Sie können die Stock `ForeColor` und `BackColor` Eigenschaften oder eigene benutzerdefinierte Farbe, wenn das Steuerelement zu zeichnen. Um eine Farbeigenschaft zu verwenden, rufen Sie die [Memberfunktion COleControl:: TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) Memberfunktion. Die Parameter dieser Funktion sind der Wert der Farbeigenschaft und ein optionales Palettenhandle. Der Rückgabewert ist eine **COLORREF** Funktionen der Wert, der an GDI übergeben werden kann, wie `SetTextColor` und `CreateSolidBrush`.  
  
 Farbwerte für die Stock `ForeColor` und `BackColor` Eigenschaften erfolgt durch Aufrufen der `GetForeColor` oder `GetBackColor` bzw. die Funktion.  
  
 Im folgende Beispiel wird veranschaulicht, verwenden diese zwei Farbeigenschaften beim Zeichnen eines Steuerelements. Initialisiert einen temporären **COLORREF** Variable und einen `CBrush` Objekt durch Aufrufe von `TranslateColor`: einer mit der `ForeColor` -Eigenschaft und der andere mit der `BackColor` Eigenschaft. Eine temporäre `CBrush` Objekt wird dann verwendet, um das Steuerelement Rechteck gezeichnet, und die Textfarbe festgelegt ist, mit der `ForeColor` Eigenschaft.  
  
 [!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]  
  
## <a name="see-also"></a>Siehe auch  
 [MFC ActiveX Controls (MFC-ActiveX-Steuerelemente)](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl-Klasse](../mfc/reference/colecontrol-class.md)
