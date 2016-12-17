---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von vordefinierten Eigenschaften"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackColor-Eigenschaft"
  - "ForeColor-Eigenschaft"
  - "Vordergrundfarben"
  - "Vordergrundfarben, ActiveX-Steuerelemente"
  - "MFC-ActiveX-Steuerelemente, Eigenschaften"
  - "Eigenschaften [MFC], Hinzufügen von Bestand"
ms.assetid: 8b98c8c5-5b69-4366-87bf-0e61e6668ecb
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von vordefinierten Eigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vordefinierte Eigenschaften unterscheiden sich von benutzerdefinierten Eigenschaften, da sie bereits über die Klasse `COleControl` implementiert werden.  `COleControl` enthält vordefinierte Memberfunktionen, die allgemeine Eigenschaften für das Steuerelement unterstützen.  Einige allgemeine Eigenschaften enthalten die Beschriftung des Steuerelements und der Vordergrund\- und Hintergrundfarben.  Informationen über andere vordefinierte Eigenschaften, finden Sie unter [Vordefinierte Eigenschaften unterstützt im Assistenten zum Hinzufügen von Eigenschaften](#_core_stock_properties_supported_by_classwizard) weiter unten in diesem Artikel.  Die Dispatchzuordnungseinträge für vordefinierte Eigenschaften werden immer von **DISP\_STOCKPROP** vorangestellt.  
  
 Dieser Artikel wird beschrieben, wie Sie eine vordefinierte Eigenschaft \(in diesem Fall, Beschriftung\) einem ActiveX\-Steuerelement mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzufügt und beschreibt die resultierenden Codeänderungen.  Folgende Themen werden behandelt:  
  
-   [Mit dem Assistenten zum Hinzufügen von Eigenschaften, um eine vordefinierte Eigenschaft hinzuzufügen](#_core_using_classwizard_to_add_a_stock_property)  
  
-   [Assistent zum Hinzufügen von Eigenschaftenen\-Änderungen für vordefinierte Eigenschaften](#_core_classwizard_changes_for_stock_properties)  
  
-   [Vordefinierte Eigenschaften unterstützt im Assistenten zum Hinzufügen von Eigenschaften](#_core_stock_properties_supported_by_classwizard)  
  
-   [Vordefinierte Eigenschaften und Benachrichtigung](#_core_stock_properties_and_notification)  
  
-   [Farbeigenschaften](#_core_color_properties)  
  
    > [!NOTE]
    >  Visual Basic\-benutzerdefinierteSteuerelemente haben normalerweise Eigenschaften wie oberen, linken, Breite, Höhe, stimmen überein, kennzeichnen, benennen, \-, Tabulation und übergeordnete Element.  ActiveX\-Steuerelementcontainer sind jedoch für das Implementieren dieser Steuerelementeigenschaften zuständig und daher sollten ActiveX\-Steuerelemente diese Eigenschaften nicht unterstützen.  
  
##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> Mit dem Assistenten zum Hinzufügen von Eigenschaften, um eine vordefinierte Eigenschaft hinzuzufügen  
 Das Hinzufügen vordefinierter Eigenschaften erfordert weniger Code als, benutzerdefinierten Eigenschaften hinzufügen, da Unterstützung für die Eigenschaft automatisch von `COleControl` behandelt wird.  Die folgende Prozedur veranschaulicht das Hinzufügen vordefinierter Beschriftungseigenschaft zu einem ActiveX\-Steuerelement\-Framework und kann auch verwendet werden, um andere vordefinierte Eigenschaften hinzuzufügen.  Ersetzen Sie den ausgewählten vordefinierten Eigenschaftennamen für Beschriftung.  
  
#### So der vordefinierten Beschriftungseigenschaft mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
     Dadurch wird unter [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  Im Feld **Eigenschaftenname** klicken Sie auf **Beschriftung**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_stock_properties"></a> Assistent zum Hinzufügen von Eigenschaftenen\-Änderungen für vordefinierte Eigenschaften  
 Da `COleControl` Stützvordefinierte Eigenschaften, dem Assistenten zum Hinzufügen von Eigenschaften nicht die Klassendeklaration in jeder Hinsicht geändert; fügt sie der Eigenschaft der Dispatchzuordnung hinzu.  Der Assistent zum Hinzufügen von Eigenschaften wird die folgende Zeile der Dispatchzuordnung des Steuerelements hinzu, das in der Implementierungsdatei \(.CPP\) ist:  
  
 [!CODE [NVC_MFC_AxUI#22](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#22)]  
  
 In der folgenden Zeile wird Ihrer Schnittstellenbeschreibung der Datei des Steuerelements \(.IDL\) hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#23](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#23)]  
  
 Diese Zeile weist der Beschriftungseigenschaft eine bestimmte ID zu  Beachten Sie, dass die Eigenschaft bereit ist und Berechtigung von der Datenbank anfordern wird, bevor der Wert geändert wird.  
  
 Dies macht die Beschriftungseigenschaft verfügbar für Benutzer des Steuerelements.  Um den Wert einer vordefinierten Eigenschaft zu verwenden, greifen Sie eine Membervariable oder eine Memberfunktion `COleControl` der Basisklasse zu.  Weitere Informationen zu dieser Membervariablen und Memberfunktionen, finden Sie im nächsten Abschnitt, vorrätigen Artikel die Eigenschaften, die vom Assistenten zum Hinzufügen von Eigenschaften unterstützt werden.  
  
##  <a name="_core_stock_properties_supported_by_classwizard"></a> Auf Lager Sie die Eigenschaften, die vom Assistenten zum Hinzufügen von Eigenschaften unterstützt werden  
 Die `COleControl`\-Klasse stellt neun vordefinierte Eigenschaften.  Sie können die Eigenschaften hinzufügen, die Sie benötigen, indem Sie den Assistenten zum Hinzufügen von Eigenschaften verwenden.  
  
|Eigenschaft|Dispatchzuordnungseintrag|Wie auf Wert zugreift|  
|-----------------|-------------------------------|---------------------------|  
|**Darstellung**|**DISP\_STOCKPROP\_APPEARANCE\(\)**|Wert zugreifbar als **m\_sAppearance**.|  
|`BackColor`|**DISP\_STOCKPROP\_BACKCOLOR\(\)**|Wert verfügbar über das Aufrufen von `GetBackColor`.|  
|`BorderStyle`|**DISP\_STOCKPROP\_BORDERSTYLE\(\)**|Wert zugreifbar als **m\_sBorderStyle**.|  
|**Beschriftung**|**DISP\_STOCKPROP\_CAPTION\(\)**|Wert verfügbar über das Aufrufen von `InternalGetText`.|  
|**Aktiviert**|**DISP\_STOCKPROP\_ENABLED\(\)**|Wert zugreifbar als **m\_bEnabled**.|  
|**Schriftart**|**DISP\_STOCKPROP\_FONT\(\)**|Siehe den Artikel [MFC\-ActiveX\-Steuerelemente: Verwenden der Schriftarten](../mfc/mfc-activex-controls-using-fonts.md) zur Verwendung.|  
|`ForeColor`|**DISP\_STOCKPROP\_FORECOLOR\(\)**|Bewerten Sie verfügbar, indem Sie `GetForeColor` aufrufen.|  
|**hWnd**|**DISP\_STOCKPROP\_HWND\(\)**|Bewerten Sie leicht als `m_hWnd`.|  
|**Text**|**DISP\_STOCKPROP\_TEXT\(\)**|Wert verfügbar über das Aufrufen von `InternalGetText`.  Diese Eigenschaft ist die **Beschriftung** entspricht, außer dem Eigenschaftennamen.|  
|**ReadyState**|**DISP\_STOCKPROP\_READYSTATE\(\)**|Wert zugreifbar als m\_lReadyState oder `GetReadyState`|  
  
##  <a name="_core_stock_properties_and_notification"></a> Vordefinierte Eigenschaften und Benachrichtigung  
 Die meisten Eigenschaften verfügen vordefinierten Benachrichtigungsfunktionen, die überschrieben werden können.  Beispielsweise wenn die `BackColor`\-Eigenschaft geändert wird, wird die `OnBackColorChanged`\-Funktion \(eine Memberfunktion der Steuerelementklasse\) bezeichnet.  Die Standardimplementierung \(in `COleControl`\) ruft `InvalidateControl` auf.  Überschreiben Sie diese Funktion, wenn Sie zusätzliche Aktionen als Reaktion auf diese Situation reagieren möchten.  
  
##  <a name="_core_color_properties"></a> Farbeigenschaften  
 Sie können vordefinierte `ForeColor` und die Eigenschaften `BackColor` verwenden oder eigene benutzerdefinierte Farbeigenschaften, wenn Sie das Steuerelement zeichnen.  Um eine Farbeigenschaft zu verwenden, erhalten Sie die Memberfunktion [COleControl::TranslateColor](../Topic/COleControl::TranslateColor.md) auf.  Die Parameter dieser Funktion sind der Wert die Farbeigenschaft und ein optionales Palettenhandle.  Der Rückgabewert ist ein **COLORREF**\-Wert, der an GDI\-Funktionen, wie `SetTextColor` und `CreateSolidBrush` übergeben werden kann.  
  
 Auf die Farbwerte für vordefinierte `ForeColor` und die `BackColor`\-Eigenschaften zugegriffen werden, indem entweder `GetForeColor` oder die `GetBackColor`\-Funktion, die jeweils aufgerufen wird.  
  
 Im folgenden Beispiel wird mit diesen beiden Farbeigenschaften, wenn ein Steuerelement gezeichnet wird.  Es initialisiert eine temporäre Variable und **COLORREF** ein `CBrush`\-Objekt durch Aufrufe von `TranslateColor`: ein mit der `ForeColor`\-Eigenschaft und die andere mit der `BackColor`\-Eigenschaft.  Ein temporäres `CBrush`\-Objekt wird dann verwendet, um das Rechteck des Steuerelements zu zeichnen, und Textfarbe wird mithilfe der `ForeColor`\-Eigenschaft festgelegt.  
  
 [!CODE [NVC_MFC_AxUI#24](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#24)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)