---
title: 'MFC-ActiveX-Steuerelemente: Eigenschaftenseite'
ms.date: 11/19/2018
helpviewer_keywords:
- DDP_ functions [MFC]
- MFC ActiveX controls [MFC], properties
- property pages [MFC], MFC ActiveX controls
- DoDataExchange method [MFC]
- OLEIVERB_PROPERTIES
- CPropertyPageDialog class [MFC]
- MFC ActiveX controls [MFC], property pages
ms.assetid: 1506f87a-9fd6-4505-8380-0dbc9636230e
ms.openlocfilehash: 7027a58960e07903c9d774e07379c8050bc489b8
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176457"
---
# <a name="mfc-activex-controls-property-pages"></a>MFC-ActiveX-Steuerelemente: Eigenschaftenseite

Eigenschaftenseiten können die Benutzer eine ActiveX-Steuerelements anzeigen und Ändern der Eigenschaften von ActiveX-Steuerelements. Diese Eigenschaften erfolgt durch den Aufruf ein Dialogfeld der Eigenschaftenseiten für eine oder mehrere enthält, die eine benutzerdefinierte grafische Schnittstelle zum Anzeigen und bearbeiten die Eigenschaften des Steuerelements bereitstellen.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Eigenschaftenseiten von ActiveX-Steuerelement werden auf zwei Arten angezeigt:

- Wenn Eigenschaften des Steuerelements-Verb (**OLEIVERB_PROPERTIES**) wird aufgerufen, das Steuerelement öffnet ein modales Dialogfeld, die Eigenschaftenseiten des Steuerelements enthält.

- Container kann ein eigenes nicht modales Dialogfeld anzeigen, das die Eigenschaftenseiten des ausgewählten Steuerelements anzeigt.

Das Dialogfeld "Eigenschaften" (in der folgenden Abbildung dargestellt) besteht aus einem Bereich für die Anzeige der aktuellen Eigenschaftenseite der Registerkarten für den Wechsel zwischen Seiten und eine Sammlung von Schaltflächen, die allgemeine Aufgaben ausführen, z. B. das Schließen der eigenschaftenseitendialog, Alle vorgenommenen Änderungen abbrechen oder sofortiges Anwenden von Änderungen auf das ActiveX-Steuerelement.

![Eigenschaftendialogfeld für Circ3](../mfc/media/vc373i1.gif "Eigenschaftendialogfeld für Circ3") <br/>
Im Dialogfeld Eigenschaften

Dieser Artikel behandelt die Themen in Bezug auf die Verwendung von Eigenschaftenseiten in einem ActiveX-Steuerelement. Dazu gehören:

- [Implementieren der Standardseite für die Eigenschaft für ein ActiveX-Steuerelement](#_core_implementing_the_default_property_page)

- [Hinzufügen von Steuerelementen zu einer Eigenschaftenseite](#_core_adding_controls_to_a_property_page)

- [Anpassen der DoDataExchange-Funktion](#_core_customizing_the_dodataexchange_function)

Weitere Informationen zur Verwendung von Eigenschaftenseiten in einem ActiveX-Steuerelement finden Sie unter den folgenden Artikeln:

- [MFC-ActiveX-Steuerelemente: Hinzufügen einer weiteren benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md)

- [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)

Informationen zum Verwenden von Eigenschaftenseiten in einer MFC-Anwendung als ein ActiveX-Steuerelement, finden Sie unter [Eigenschaftenblätter](../mfc/property-sheets-mfc.md).

##  <a name="_core_implementing_the_default_property_page"></a> Implementieren die Standard-Eigenschaftenseite

Wenn Sie den ActiveX-Steuerelement-Assistenten verwenden, um das Projekt zu erstellen, bietet der ActiveX-Steuerelement-Assistent eine Standardklasse für Eigenschaftenseiten für das Steuerelement abgeleitet [COlePropertyPage-Klasse](../mfc/reference/colepropertypage-class.md). Zunächst diese Eigenschaftenseite ist leer, aber Sie können alle Dialogfeld-Steuerelement oder eine Gruppe von Steuerelementen, ihm hinzufügen. Da der ActiveX-Steuerelement-Assistent Page-Klasse nur eine Eigenschaft wird standardmäßig eine zusätzliche Eigenschaft Page-Klassen erstellt (auch abgeleitet `COlePropertyPage`) muss der Klassenansicht erstellt werden. Weitere Informationen zu dieser Vorgehensweise finden Sie unter [MFC-ActiveX-Steuerelemente: Hinzufügen von einem anderen benutzerdefinierten Eigenschaftenseite](../mfc/mfc-activex-controls-adding-another-custom-property-page.md).

Implementieren einer Eigenschaft Seite (in diesem Fall wird der Standardwert) ist ein dreistufiger Prozess:

#### <a name="to-implement-a-property-page"></a>Implementieren eine Eigenschaftenseite

1. Hinzufügen einer `COlePropertyPage`-abgeleiteten Klasse in das Projekt. Wenn das Projekt mit dem ActiveX-Steuerelement-Assistenten (wie in diesem Fall) erstellt wurde, ist der Standard-Eigenschaftenklasse von Seite bereits vorhanden.

1. Verwenden Sie den Dialog-Editor, um alle Steuerelemente an der Eigenschaftenseitenvorlage hinzuzufügen.

1. Anpassen der `DoDataExchange` Funktion der `COlePropertyPage`-abgeleitete Klasse zum Austauschen von Werten zwischen dem Eigenschaftenseiten-Steuerelement und das ActiveX-Steuerelement.

Zwecke verwenden, die folgenden Verfahren wird z. B. ein einfaches Steuerelement, das (mit dem Namen "Sample") verwenden. Beispiel mit dem ActiveX-Steuerelement-Assistenten erstellt wurde, und enthält nur die vordefinierte Caption-Eigenschaft.

##  <a name="_core_adding_controls_to_a_property_page"></a> Hinzufügen von Steuerelementen zu einer Eigenschaftenseite

#### <a name="to-add-controls-to-a-property-page"></a>Zum Hinzufügen von Steuerelementen auf einer Eigenschaftenseite

1. Öffnen Sie mit dem Steuerelementprojekt öffnen Ressourcenansicht nutzen zu können.

1. Doppelklicken Sie auf die **Dialogfeld** Directory-Symbol.

1. Öffnen Sie das Dialogfeld IDD_PROPPAGE_SAMPLE.

   Der ActiveX-Steuerelement-Assistent fügt den Namen des Projekts an das Ende der Dialogfeld-ID, in diesem Fall Beispiel.

1. Ziehen Sie und legen Sie des ausgewählten Steuerelements aus der Toolbox auf das Dialogfeldbereich ab.

1. In diesem Beispiel eine Textdatei beschriftungs-Steuerelement "Caption:" und ein Steuerelement mit Eingabefeld mit einer ID, IDC_CAPTION sind ausreichend.

1. Klicken Sie auf **speichern** auf der Symbolleiste, um die Änderungen zu speichern.

Nun, dass die Benutzeroberfläche geändert wurde, müssen Sie im Bearbeitungsfeld mit die Caption-Eigenschaft zu verknüpfen. Dies erfolgt im folgenden Abschnitt durch Bearbeiten der `CSamplePropPage::DoDataExchange` Funktion.

##  <a name="_core_customizing_the_dodataexchange_function"></a> Anpassen der DoDataExchange-Funktion

Ihr Eigenschaftenseite [Ddx_managedcontrol](../mfc/reference/cwnd-class.md#dodataexchange) -Funktion können Sie Eigenschaftswerte über die Seite durch die tatsächlichen Werte der Eigenschaften, die im Steuerelement zu verknüpfen. Um Verbindungen herzustellen, müssen Sie die entsprechende Seite Eigenschaftenfelder ihre entsprechenden Steuerelementeigenschaften zuordnen.

Diese Zuordnungen werden implementiert, über die Eigenschaftenseite **DDP_** Funktionen. Die **DDP_** Funktionen funktionieren, wie die **DDX_** Funktionen, die in standardmäßigen MFC-Dialogfeldern, mit einer Ausnahme verwendet. Zusätzlich zu den Verweis auf eine Membervariable zu **DDP_** Funktionen haben den Namen der Steuerelementeigenschaft. Im folgenden finden Sie ein typischer Eintrag in der `DoDataExchange` -Funktion für eine Eigenschaftenseite.

[!code-cpp[NVC_MFC_AxUI#31](../mfc/codesnippet/cpp/mfc-activex-controls-property-pages_1.cpp)]

Diese Funktion wird der Eigenschaftenseite *M_caption* Membervariable, die mit der Beschriftung mit der `DDP_TEXT` Funktion.

Nachdem Sie die Eigenschaftenseiten-Steuerelement eingefügt haben, müssen Sie eine Verknüpfung zwischen dem Eigenschaftenseiten-Steuerelement, IDC_CAPTION und der tatsächlichen Steuerelementeigenschaft einrichten-Beschriftung mithilfe der `DDP_Text` wie oben beschrieben funktioniert.

[Eigenschaftenseiten](../mfc/reference/property-pages-mfc.md) stehen für andere Steuerelementtypen für Dialogfelder, z. B. Kontrollkästchen, Optionsfelder und Listenfelder. Die folgende Tabelle enthält den gesamten Satz von Eigenschaftenseite **DDP_** Funktionen und ihren Zweck:

### <a name="property-page-functions"></a>Funktionen von Eigenschaftenseiten

|Funktionsname|Mit dieser Funktion können verknüpfen|
|-------------------|-------------------------------|
|`DDP_CBIndex`|Die ausgewählte Zeichenfolge Index in einem Kombinationsfeld mit einer Steuerelementeigenschaft.|
|`DDP_CBString`|Die ausgewählte Zeichenfolge in einem Kombinationsfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge kann mit den Buchstaben des Eigenschaftswerts beginnen jedoch muss nicht vollständig damit übereinstimmen.|
|`DDP_CBStringExact`|Die ausgewählte Zeichenfolge in einem Kombinationsfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|
|`DDP_Check`|Ein Kontrollkästchen mit einer Steuerelementeigenschaft.|
|`DDP_LBIndex`|Die ausgewählte Zeichenfolge Index in einem Listenfeld mit einer Steuerelementeigenschaft.|
|`DDP_LBString`|Die ausgewählte Zeichenfolge in einem Listenfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge kann mit den Buchstaben des Eigenschaftswerts beginnen jedoch muss nicht vollständig damit übereinstimmen.|
|`DDP_LBStringExact`|Die ausgewählte Zeichenfolge in einem Listenfeld mit einer Steuerelementeigenschaft. Die ausgewählte Zeichenfolge und den Wert der Eigenschaft Zeichenfolge müssen genau übereinstimmen.|
|`DDP_Radio`|Ein Optionsfeld mit einer Steuerelementeigenschaft.|
|`DDP_Text`|Text mit einer Steuerelementeigenschaft.|

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[COlePropertyPage-Klasse](../mfc/reference/colepropertypage-class.md)
