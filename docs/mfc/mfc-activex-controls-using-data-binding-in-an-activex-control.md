---
title: 'MFC-ActiveX-Steuerelemente: Verwenden der Datenbindung in einem ActiveX-Steuerelement'
ms.date: 09/12/2018
f1_keywords:
- bindable
- requestedit
- defaultbind
- displaybind
- dispid
helpviewer_keywords:
- MFC ActiveX controls [MFC], data binding
- data binding [MFC], MFC ActiveX controls
- data-bound controls [MFC], MFC ActiveX controls
- controls [MFC], data binding
- bound controls [MFC], MFC ActiveX
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
ms.openlocfilehash: 54cfbc6d31c0c86163400df691dec47e0c093d36
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603657"
---
# <a name="mfc-activex-controls-using-data-binding-in-an-activex-control"></a>MFC-ActiveX-Steuerelemente: Verwenden der Datenbindung in einem ActiveX-Steuerelement

Einer der leistungsfähigere Verwendungszwecke von ActiveX-Steuerelementen ist die Datenbindung, wodurch eine Eigenschaft des Steuerelements an ein bestimmtes Feld in einer Datenbank gebunden werden soll. Wenn ein Benutzer Daten in dieser gebundenen Eigenschaft ändert, benachrichtigt das Steuerelement an die Datenbank und fordert an, dass der Datensatz das Feld aktualisiert werden. Anschließend benachrichtigt die Datenbank, die Kontrolle über den Erfolg oder Misserfolg der Anforderung.

>[!IMPORTANT]
> ActiveX ist eine veraltete Technologie, die nicht für Neuentwicklungen verwendet werden soll. Weitere Informationen zu moderne Technologien, die ActiveX-ablösen, finden Sie unter [ActiveX-Steuerelemente](activex-controls.md).

Dieser Artikel behandelt die Steuerelement-Seite Ihrer Aufgabe. Implementieren die Daten binden von Interaktionen mit der Datenbank ist die Verantwortung für den Steuerelementcontainer. Wie Sie die Interaktionen mit der Datenbank in Ihrem Container verwalten, ist über den Rahmen dieser Dokumentation hinaus. Wie Sie das Steuerelement für die Datenbindung vorbereiten, werden im Rest dieses Artikels erläutert.

![Konzeptuelles Diagramm eines&#45;gebundenes Steuerelement](../mfc/media/vc374v1.gif "vc374v1") Konzeptuelles Diagramm eines datengebundenen Steuerelements

Die `COleControl` Klasse enthält zwei Memberfunktionen, mit denen einen einfachen Prozess zum Implementieren der Datenbindung. Die erste Funktion, [BoundPropertyRequestEdit](../mfc/reference/colecontrol-class.md#boundpropertyrequestedit), zum Anfordern von Berechtigungen so ändern Sie den Wert der Eigenschaft verwendet wird. [BoundPropertyChanged](../mfc/reference/colecontrol-class.md#boundpropertychanged), die zweite Funktion wird aufgerufen, nachdem Sie den Wert der Eigenschaft erfolgreich geändert wurde.

In diesem Artikel werden die folgenden Themen behandelt:

- [Erstellen eine bindbare Eigenschaft](#vchowcreatingbindablestockproperty)

- [Erstellen eine bindbare Get-/Set-Methode](#vchowcreatingbindablegetsetmethod)

##  <a name="vchowcreatingbindablestockproperty"></a> Erstellen eine bindbare Eigenschaft

Es ist möglich, eine datengebundene Eigenschaft, zu erstellen, obwohl es wahrscheinlicher ist, dass Sie sollten eine [bindbare Get/Set-Methode](#vchowcreatingbindablegetsetmethod).

> [!NOTE]
>  Vordefinierte Eigenschaften haben die `bindable` und `requestedit` Attribute standardmäßig.

#### <a name="to-add-a-bindable-stock-property-using-the-add-property-wizard"></a>Um eine bindbare Eigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzuzufügen.

1. Beginnen Sie ein Projekt mit der [MFC-ActiveX-Steuerelement-Assistent](../mfc/reference/mfc-activex-control-wizard.md).

1. Mit der rechten Maustaste in des Schnittstellenknoten für das Steuerelement.

   Dadurch wird das Kontextmenü geöffnet.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

1. Wählen Sie einen der Einträge aus der **Eigenschaftennamen** Dropdown-Liste. Sie können beispielsweise auswählen **Text**.

   Da **Text** ist eine vordefinierte Eigenschaft, die **bindbare** und **Requestedit** Attribute sind automatisch ausgewählt.

1. Wählen Sie die folgenden Kontrollkästchen aus der **IDL-Attribute** Registerkarte: **Displaybind** und **Defaultbind** die Attribute der Eigenschaftsdefinition im des Projekts hinzu. IDL-Datei. Diese Attribute stellen das Steuerelement für den Benutzer sichtbar und der vordefinierten Eigenschaft die bindbare Standardeigenschaft.

An diesem Punkt wird das Steuerelement kann Daten aus einer Datenquelle anzeigen, aber der Benutzer wird nicht in der Lage, die Datenfelder zu aktualisieren. Wenn Sie möchten das Steuerelement in der auch in der Lage, Daten aktualisieren, ändern Sie die `OnOcmCommand` [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) Funktion, die wie folgt aussehen:

[!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

Sie können jetzt das Projekt erstellen, das das Steuerelement registriert wird. Beim Einfügen des Steuerelements in einem Dialogfeld der **Datenfeld** und **Datenquelle** werden wurden Eigenschaften hinzugefügt, und Sie können jetzt auswählen, eine Datenquelle und ein Feld in das Steuerelement angezeigt.

##  <a name="vchowcreatingbindablegetsetmethod"></a> Erstellen eine bindbare Get-/Set-Methode

Sie können auch erstellen, zusätzlich zu einem datengebundenen get-/Set-Methode, eine [bindbare Eigenschaft](#vchowcreatingbindablestockproperty).

> [!NOTE]
>  Dieses Verfahren setzt voraus, dass Sie ein ActiveX-Steuerelement, Unterklassen ein Steuerelements für die Windows-Projekt verfügen.

#### <a name="to-add-a-bindable-getset-method-using-the-add-property-wizard"></a>Zum Hinzufügen einer bindbaren get-/Set-Methode, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften

1. Laden Sie das Steuerelementprojekt.

1. Auf der **Steuerelementeinstellungen** Seite, wählen Sie eine Fensterklasse für das Steuerelement, um eine Unterklasse. Z. B. empfiehlt um eine Unterklasse ein Bearbeitungssteuerelement.

1. Laden Sie das Steuerelementprojekt.

1. Mit der rechten Maustaste in des Schnittstellenknoten für das Steuerelement.

   Dadurch wird das Kontextmenü geöffnet.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

1. Geben Sie den Namen der Eigenschaft in der **Eigenschaftennamen** Feld. Verwendung `MyProp` für dieses Beispiel.

1. Wählen Sie einen Datentyp aus der **Eigenschaftentyp** im Dropdown Listenfeld. Verwendung **kurze** für dieses Beispiel.

1. Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.

9. Wählen Sie auf der Registerkarte "IDL-Attribute" die folgenden Kontrollkästchen: **bindbare**, **Requestedit**, **Displaybind**, und **Defaultbind** hinzufügen die Attribute auf die Eigenschaftsdefinition des Projekts. IDL-Datei. Diese Attribute stellen das Steuerelement für den Benutzer sichtbar und der vordefinierten Eigenschaft die bindbare Standardeigenschaft.

10. Klicken Sie auf **Fertig stellen**.

11. Ändern Sie den Hauptteil der `SetMyProp` Funktion so, dass sie den folgenden Code enthält:

   [!code-cpp[NVC_MFC_AxData#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_2.cpp)]

12. Der Parameter zu übergeben, um die `BoundPropertyChanged` und `BoundPropertyRequestEdit` Functions ist die Dispid der Eigenschaft, das den Parameter an die übergeben werden, für die Eigenschaft in der. IDL-Datei.

13. Ändern der [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md) funktionieren, sodass sie den folgenden Code enthält:

   [!code-cpp[NVC_MFC_AxData#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_1.cpp)]

14. Ändern der `OnDraw` Funktion so, dass sie den folgenden Code enthält:

   [!code-cpp[NVC_MFC_AxData#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_3.cpp)]

15. Fügen Sie mit dem öffentlichen Abschnitt der Headerdatei die Headerdatei für eine Klasse die folgenden Definitionen (Konstruktoren) für die Membervariablen hinzu:

   [!code-cpp[NVC_MFC_AxData#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_4.h)]

16. Stellen Sie der folgenden Zeile die letzte Zeile in der `DoPropExchange` Funktion:

   [!code-cpp[NVC_MFC_AxData#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_5.cpp)]

17. Ändern der `OnResetState` Funktion so, dass sie den folgenden Code enthält:

   [!code-cpp[NVC_MFC_AxData#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_6.cpp)]

18. Ändern der `GetMyProp` Funktion so, dass sie den folgenden Code enthält:

   [!code-cpp[NVC_MFC_AxData#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-data-binding-in-an-activex-control_7.cpp)]

Sie können jetzt das Projekt erstellen, das das Steuerelement registriert wird. Beim Einfügen des Steuerelements in einem Dialogfeld der **Datenfeld** und **Datenquelle** werden wurden Eigenschaften hinzugefügt, und Sie können jetzt auswählen, eine Datenquelle und ein Feld in das Steuerelement angezeigt.

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

