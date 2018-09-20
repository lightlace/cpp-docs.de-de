---
title: 'MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften | Microsoft-Dokumentation'
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
ms.openlocfilehash: 4100dc14a25a744e5c28ffd1b16119408d800656
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46404513"
---
# <a name="mfc-activex-controls-adding-stock-properties"></a>MFC-ActiveX-Steuerelemente: Hinzufügen von vordefinierten Eigenschaften

Vordefinierte Eigenschaften unterscheiden sich von benutzerdefinierten Eigenschaften, da sie bereits von der Klasse implementiert werden `COleControl`. `COleControl` enthält vordefinierte Memberfunktionen, allgemeine Eigenschaften für das Steuerelement zu unterstützen. Einige allgemeinen Eigenschaften enthalten die Beschriftung des Steuerelements und der Vordergrund- und Hintergrundfarben an. Weitere Informationen über weitere vordefinierten Eigenschaften finden Sie unter [Stock Eigenschaften unterstützt, indem Sie den Assistenten zum Hinzufügen einer Eigenschaft](#_core_stock_properties_supported_by_classwizard) weiter unten in diesem Artikel. Der Verteilungs-Zuordnungseinträge für vordefinierte Eigenschaften immer DISP_STOCKPROP vorangestellt.

In diesem Artikel wird beschrieben, wie eine Systemeigenschaft (in diesem Fall die Beschriftung) ein ActiveX-Steuerelement mit dem Assistenten zum Hinzufügen von Eigenschaften hinzu, und es wird erläutert, die sich ergebende codeänderungen. Folgende Themen werden behandelt:

- [Verwenden den Assistenten zum Hinzufügen einer Eigenschaft zum Hinzufügen von einer Systemeigenschaft](#_core_using_classwizard_to_add_a_stock_property)

- [Hinzufügen von Eigenschaften-Assistenten-Änderungen für die vordefinierten Eigenschaften](#_core_classwizard_changes_for_stock_properties)

- [Vordefinierte Eigenschaften, die von der Assistent zum Hinzufügen von Eigenschaften unterstützt werden](#_core_stock_properties_supported_by_classwizard)

- [Vordefinierte Eigenschaften und Benachrichtigung](#_core_stock_properties_and_notification)

- [Farbformatierung](#_core_color_properties)

    > [!NOTE]
    >  Benutzerdefinierte Steuerelemente in Visual Basic haben in der Regel Eigenschaften wie oben, links, Breite, Höhe, ausrichten, Tag, Name, TabIndex, TabStop und übergeordneten. ActiveX-Steuerelementcontainer, allerdings für die Implementierung dieser Eigenschaften des Steuerelements verantwortlich sind und daher ActiveX-Steuerelemente sollten diese Eigenschaften nicht unterstützt.

##  <a name="_core_using_classwizard_to_add_a_stock_property"></a> Mithilfe der Eigenschaft-Assistenten zum Hinzufügen einer vordefinierten Eigenschaft hinzufügen

Hinzufügen von vordefinierten Eigenschaften erfordert weniger Code als benutzerdefinierte Eigenschaften hinzufügen, da die Unterstützung für die Eigenschaft automatisch vom erfolgt `COleControl`. Das folgende Verfahren veranschaulicht, wie Sie auf ein ActiveX-Steuerelement-Framework die Stock "Caption"-Eigenschaft hinzugefügt und kann auch verwendet werden, um weitere vordefinierten Eigenschaften hinzuzufügen. Ersetzen Sie den Namen der ausgewählten Eigenschaft für die Beschriftung an.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Um die vordefinierten Caption-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzuzufügen.

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

     Daraufhin wird die [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).

1. In der **Eigenschaftennamen** auf **Beschriftung**.

1. Klicken Sie auf **Fertig stellen**.

##  <a name="_core_classwizard_changes_for_stock_properties"></a> Hinzufügen von Assistenten Eigenschaftenänderungen für Basiseigenschaften

Da `COleControl` unterstützt Basiseigenschaften, den Assistenten zum Hinzufügen einer Eigenschaft ändert sich nicht auf die Klassendeklaration in keiner Weise; die Dispatchzuordnung die Eigenschaft hinzugefügt. Der Assistent zum Hinzufügen von Eigenschaften fügt die folgende Zeile, um die Dispatchzuordnung der das Steuerelement, das in der Implementierung befindet (. CPP)-Datei:

[!code-cpp[NVC_MFC_AxUI#22](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_1.cpp)]

Die folgende Zeile wird die schnittstellenbeschreibung des Steuerelements hinzugefügt (. IDL)-Datei:

[!code-cpp[NVC_MFC_AxUI#23](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_2.idl)]

Diese Zeile weist der Caption-Eigenschaft eine bestimmte ID Beachten Sie, dass die Eigenschaft gebunden werden kann, und Berechtigung aus der Datenbank fordert vor dem Ändern des Werts.

Dadurch wird die Caption-Eigenschaft für Benutzer des Steuerelements verfügbar. Um den Wert einer vordefinierten Eigenschaft verwenden zu können, Zugriff auf, eine Membervariable oder eine Memberfunktion der `COleControl` Basisklasse. Weitere Informationen zu diesen Membervariablen und Memberfunktionen finden Sie im nächsten Abschnitt Stock Eigenschaften unterstützt, indem Sie den Assistenten zum Hinzufügen einer Eigenschaft.

##  <a name="_core_stock_properties_supported_by_classwizard"></a> Vordefinierte Eigenschaften, die von unterstützt die Eigenschaft Assistent zum Hinzufügen von

Die `COleControl` Klasse stellt neun Basiseigenschaften bereit. Sie können die Eigenschaften hinzufügen, die mithilfe des Assistenten zum Hinzufügen einer Eigenschaft verwendet werden sollen.

|Eigenschaft|Dispatch-Zuordnungseintrag|Gewusst wie: Zugriff auf Wert|
|--------------|------------------------|-------------------------|
|`Appearance`|DISP_STOCKPROP_APPEARANCE)|Wert als `m_sAppearance`.|
|`BackColor`|DISP_STOCKPROP_BACKCOLOR)|Wert zugegriffen werden kann, durch den Aufruf `GetBackColor`.|
|`BorderStyle`|DISP_STOCKPROP_BORDERSTYLE)|Wert als `m_sBorderStyle`.|
|`Caption`|DISP_STOCKPROP_CAPTION)|Wert zugegriffen werden kann, durch den Aufruf `InternalGetText`.|
|`Enabled`|DISP_STOCKPROP_ENABLED)|Wert als `m_bEnabled`.|
|`Font`|DISP_STOCKPROP_FONT)|Finden Sie im Artikel [MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten](../mfc/mfc-activex-controls-using-fonts.md) für die Nutzung.|
|`ForeColor`|DISP_STOCKPROP_FORECOLOR)|Wert zugegriffen werden kann, durch den Aufruf `GetForeColor`.|
|`hWnd`|DISP_STOCKPROP_HWND)|Wert als `m_hWnd`.|
|`Text`|DISP_STOCKPROP_TEXT)|Wert zugegriffen werden kann, durch den Aufruf `InternalGetText`. Diese Eigenschaft entspricht dem `Caption`, mit Ausnahme der Eigenschaftenname.|
|`ReadyState`|DISP_STOCKPROP_READYSTATE()|Wert als `m_lReadyState` oder `GetReadyState`|

##  <a name="_core_stock_properties_and_notification"></a> Vordefinierte Eigenschaften und Benachrichtigung

Die meisten vordefinierte Eigenschaften haben Notification-Funktionen, die überschrieben werden können. Z. B. bei jedem der `BackColor` -Eigenschaft geändert wird, die `OnBackColorChanged` Funktion (eine Memberfunktion der Steuerelement-Klasse) wird aufgerufen. Die Standardimplementierung (in `COleControl`) Aufrufe `InvalidateControl`. Überschreiben Sie diese Funktion, wenn Sie zusätzliche Aktionen als Reaktion auf diese Situation ausführen möchten.

##  <a name="_core_color_properties"></a> Farbformatierung

Sie können die Aktie `ForeColor` und `BackColor` Eigenschaften oder eigene benutzerdefinierte Farbe, wenn das Steuerelement zu zeichnen. Um eine Color-Eigenschaft zu verwenden, rufen die [Memberfunktion COleControl:: TranslateColor](../mfc/reference/colecontrol-class.md#translatecolor) Member-Funktion. Die Parameter dieser Funktion gibt den Wert der Farbeigenschaft und ein Palettenhandle optional an. Der Rückgabewert ist ein **COLORREF** Funktionen der Wert, der an GDI übergeben werden kann, wie z. B. `SetTextColor` und `CreateSolidBrush`.

Die Farbwerte für die Aktie `ForeColor` und `BackColor` erfolgt durch Aufrufen der `GetForeColor` oder `GetBackColor` ordnungsgemäß verwendet werden, bzw.

Das folgende Beispiel zeigt, verwenden diese zwei Eigenschaften aus, wenn ein Steuerelement zu zeichnen. Initialisiert ein temporäres **COLORREF** Variable und ein `CBrush` Objekt mit Aufrufen von `TranslateColor`: mithilfe der `ForeColor` -Eigenschaft und der andere mit der `BackColor` Eigenschaft. Eine temporäre `CBrush` Objekt wird dann verwendet, um das Rechteck des Steuerelements zu zeichnen und die Textfarbe festgelegt ist, mit der `ForeColor` Eigenschaft.

[!code-cpp[NVC_MFC_AxUI#24](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-properties_3.cpp)]

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)<br/>
[MFC-ActiveX-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)<br/>
[COleControl-Klasse](../mfc/reference/colecontrol-class.md)
