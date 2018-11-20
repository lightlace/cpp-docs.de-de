---
title: 'MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten'
ms.date: 11/19/2018
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
helpviewer_keywords:
- notifications [MFC], MFC ActiveX controls fonts
- OnDraw method, MFC ActiveX controls
- InternalFont method [MFC]
- SetFont method [MFC]
- OnFontChanged method [MFC]
- IPropertyNotifySink class [MFC]
- MFC ActiveX controls [MFC], fonts
- Stock Font property [MFC]
- HeadingFont property [MFC]
- GetFont method [MFC]
- SelectStockFont method [MFC]
- fonts [MFC], ActiveX controls
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
ms.openlocfilehash: 9fb7668f65b04372b87059034c3ec6cd20abc48d
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175820"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten

Wenn das ActiveX-Steuerelement Text anzeigt, können Sie die Benutzer des Steuerelements die Textdarstellung zu ändern, indem Sie eine Font-Eigenschaft ändern. Schriftarteigenschaften werden als Schriftartenobjekte implementiert, und kann eine von zwei Typen: standardmäßigen oder benutzerdefinierten. Stock Schriftart-Eigenschaften sind bereits Eigenschaften, die Sie hinzufügen können, verwenden den Assistenten zum Hinzufügen einer Eigenschaft. Benutzerdefinierte Schriftart-Eigenschaften sind nicht vorimplementiert, und Entwickler des Steuerelements bestimmt wird, Verhalten und die Verwendung der Eigenschaft.

In diesem Artikel werden die folgenden Themen behandelt:

- [Mithilfe der Stock Font-Eigenschaft](#_core_using_the_stock_font_property)

- [Verwenden die benutzerdefinierte Schriftart-Eigenschaften in das Steuerelement](#_core_implementing_a_custom_font_property)

##  <a name="_core_using_the_stock_font_property"></a> Verwenden die vordefinierte Schriftarteigenschaft

Vordefinierte Schriftart-Eigenschaften werden von der Klasse vorimplementiert [COleControl](../mfc/reference/colecontrol-class.md). Darüber hinaus ist eine Standardeigenschaftenseite ebenfalls verfügbar, damit der Benutzer verschiedene Attribute der Schriftart-Objekts, z. B. Name, Größe und Stil zu ändern.

Zugriff auf das Schriftartobjekt "über die [GetFont](../mfc/reference/colecontrol-class.md#getfont), [SetFont](../mfc/reference/colecontrol-class.md#setfont), und [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) Funktionen `COleControl`. Der Benutzer des Steuerelements greift der Font-Objekt über die `GetFont` und `SetFont` Funktionen in die gleiche Weise wie jede andere Get/Set-Eigenschaft. Wenn Sie den Zugriff auf die Schriftartobjekt in einem Steuerelement erforderlich ist, verwenden die `InternalGetFont` Funktion.

Siehe [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md), Hinzufügen von vordefinierten Eigenschaften ist einfach, mit der [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md). Wählen Sie die Schriftart-Eigenschaft, und der Assistent zum Hinzufügen von Eigenschaften fügt automatisch den vordefinierten Schriftart-Eintrag in die Dispatchzuordnung der des Steuerelements.

#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>Um die vordefinierte Schriftarteigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzuzufügen.

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

   Daraufhin wird der Assistent zum Hinzufügen von Eigenschaften.

1. In der **Eigenschaftennamen** auf **Schriftart**.

1. Klicken Sie auf **Fertig stellen**.

Der Assistent zum Hinzufügen von Eigenschaften hinzugefügt des Steuerelements Dispatchzuordnung, befindet sich in der Implementierungsdatei des Steuerelements-Klasse die folgende Zeile:

[!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]

Darüber hinaus fügt der Assistent zum Hinzufügen von Eigenschaften die folgende Zeile, auf das Steuerelement. IDL-Datei:

[!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]

Die vordefinierte Caption-Eigenschaft ist ein Beispiel für eine Texteigenschaft, die mithilfe von Informationen über den vordefinierten Eigenschaft gezeichnet werden kann. Hinzufügen der Aktie Caption-Eigenschaft zum Steuerelement verwendet Schritte ähneln denen für die Stock Font-Eigenschaft verwendet.

#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Um die vordefinierten Caption-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzuzufügen.

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

   Daraufhin wird der Assistent zum Hinzufügen von Eigenschaften.

1. In der **Eigenschaftennamen** auf **Beschriftung**.

1. Klicken Sie auf **Fertig stellen**.

Der Assistent zum Hinzufügen von Eigenschaften hinzugefügt des Steuerelements Dispatchzuordnung, befindet sich in der Implementierungsdatei des Steuerelements-Klasse die folgende Zeile:

[!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]

##  <a name="_core_modifying_the_ondraw_function"></a> Ändern die OnDraw-Funktion

Die standardmäßige Implementierung des `OnDraw` verwendet die Windows-System-Schriftart für den gesamten Text im Steuerelement angezeigt. Dies bedeutet, dass die ändern, müssen Sie die `OnDraw` Code, indem Sie den Schriftartobjekt in den Gerätekontext auswählen. Zu diesem Zweck rufen [COleControl:: SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont) und Gerätekontext, die dem Steuerelement zu übergeben, wie im folgenden Beispiel gezeigt:

[!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]

Nach der `OnDraw` Funktion wurde geändert, um die Schriftartobjekt zu verwenden, sämtlicher Text im Steuerelement mit Eigenschaften von stock Font-Eigenschaft des Steuerelements angezeigt wird.

##  <a name="_core_using_custom_font_properties_in_your_control"></a> Verwenden die benutzerdefinierte Schriftart-Eigenschaften in das Steuerelement

Zusätzlich zu die vordefinierte Schriftarteigenschaft haben das ActiveX-Steuerelement benutzerdefinierte Schriftart-Eigenschaften. Zum Hinzufügen einer benutzerdefinierten Schriftart-Eigenschaft müssen Sie folgende Aktionen ausführen:

- Verwenden Sie den Assistenten zum Hinzufügen einer Eigenschaft, um die benutzerdefinierte Schriftart-Eigenschaft zu implementieren.

- [Verarbeiten von Benachrichtigungen des Schriftart](#_core_processing_font_notifications).

- [Implementieren eine neue Benachrichtigungsschnittstelle](#_core_implementing_a_new_font_notification_interface).

###  <a name="_core_implementing_a_custom_font_property"></a> Implementieren einer benutzerdefinierten Schriftart-Eigenschaft

Um eine benutzerdefinierte Schriftarteigenschaft zu implementieren, verwenden Sie den Assistenten zum Hinzufügen einer Eigenschaft, fügen Sie die Eigenschaft, und stellen Sie dann einige Änderungen am Code. In den folgenden Abschnitten wird beschrieben, wie Sie die benutzerdefinierte hinzufügen- `HeadingFont` Eigenschaft, um die Beispiel-Steuerelement.

##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>Die benutzerdefinierte Schriftart-Eigenschaft, die über den Assistenten zum Hinzufügen einer Eigenschaft hinzufügen

1. Laden Sie das Steuerelementprojekt.

1. Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.

1. Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.

   Daraufhin wird der Assistent zum Hinzufügen von Eigenschaften.

1. In der **Eigenschaftennamen** geben einen Namen für die Eigenschaft. In diesem Beispiel verwenden **HeadingFont**.

1. Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.

1. In der **Eigenschaftentyp** Kontrollkästchen **IDispatch** <strong>\*</strong> für den Typ der Eigenschaft.

1. Klicken Sie auf **Fertig stellen**.

Der Assistent zum Hinzufügen von Eigenschaften erstellt den Code zum Hinzufügen der `HeadingFont` benutzerdefinierte Eigenschaft, um die `CSampleCtrl` Klasse und das Beispiel. IDL-Datei. Da `HeadingFont` ist ein Typ für den Get/Set-Eigenschaft, ändert der Assistent zum Hinzufügen von Eigenschaften der `CSampleCtrl` Klasse Dispatchzuordnung sollen eine DISP_PROPERTY_EX_ID[DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex) Makro-Eintrag:

[!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]

Ordnet die DISP_PROPERTY_EX-Makro die `HeadingFont` Eigenschaftennamen mit den entsprechenden `CSampleCtrl` Klasse abrufen und Festlegen von Methoden, `GetHeadingFont` und `SetHeadingFont`. Der Typ des Eigenschaftswerts ist ebenfalls angegeben. In diesem Fall VT_FONT.

Der Assistent zum Hinzufügen von Eigenschaften fügt auch eine Deklaration in der Steuerelement-Headerdatei (. H) für die `GetHeadingFont` und `SetHeadingFont` Funktionen und fügt Sie ihre Vorlagen in der Implementierungsdatei des Steuerelements (. CPP):

[!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]

Schließlich ändert der Assistent zum Hinzufügen von Eigenschaften des Steuerelements. IDL-Datei durch Hinzufügen eines Eintrags für die `HeadingFont` Eigenschaft:

[!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]

### <a name="modifications-to-the-control-code"></a>Änderungen an der Steuerungscode

Nun, da Sie hinzugefügt haben, die `HeadingFont` Eigenschaft des Steuerelements, müssen Sie einige Änderungen vornehmen, den Header- und Implementierungsdateien um Dateien zu steuern, die neue Eigenschaft vollständig unterstützt.

In der Steuerelement-Headerdatei (. H), fügen Sie die folgende Deklaration einer Variablen für die geschützten Member hinzu:

[!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]

In der Implementierungsdatei des Steuerelements (. CPP), gehen Sie folgendermaßen vor:

- Initialisieren Sie *M_fontHeading* im Konstruktor Steuerelements.

   [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]

- Deklarieren Sie eine statische FONTDESC-Struktur, die Default-Attribute der Schriftart enthält.

   [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]

- Im Steuerelement `DoPropExchange` Member funktioniert, fügen Sie einen Aufruf an die `PX_Font` Funktion. Dies bietet Initialisierung und Persistenz für die benutzerdefinierte Schriftart-Eigenschaft.

   [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]

- Schließen Sie die Implementierung des Steuerelements `GetHeadingFont` Member-Funktion.

   [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]

- Schließen Sie die Implementierung des Steuerelements `SetHeadingFont` Member-Funktion.

   [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]

- Ändern Sie das Steuerelement `OnDraw` Memberfunktion versucht, eine Variable für die zuvor ausgewählte Schriftart zu definieren.

   [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]

- Ändern Sie das Steuerelement `OnDraw` Memberfunktion versucht, die benutzerdefinierte Schriftart in den Gerätekontext wählen, durch das Hinzufügen der folgenden Zeile, wenn die Schriftart ist, verwendet werden soll.

   [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]

- Ändern Sie das Steuerelement `OnDraw` Memberfunktion versucht, wählen Sie die vorherige Schriftart zurück in den Gerätekontext, indem Sie die folgende Zeile hinzufügen, nachdem die Schriftart verwendet wurde.

   [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]

Nachdem die benutzerdefinierte Schriftart-Eigenschaft implementiert wurde, sollte die Standardeigenschaftenseite implementiert werden, können Benutzer steuern können, um aktuelle Schriftart des Steuerelements zu ändern. Um die Eigenschaftenseiten-ID für die Standardeigenschaftenseite hinzuzufügen, fügen Sie die folgende Zeile nach dem BEGIN_PROPPAGEIDS-Makro ein:

[!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]

Außerdem müssen Sie den Count-Parameter, der Ihre BEGIN_PROPPAGEIDS-Makro um eins erhöhen. Die folgende Zeile veranschaulicht dies:

[!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]

Nachdem diese Änderungen vorgenommen wurden, erstellen Sie das gesamte Projekt aus, um die zusätzliche Funktionalität integrieren neu.

###  <a name="_core_processing_font_notifications"></a> Verarbeiten von Benachrichtigungen der Schriftart

In den meisten Fällen muss das Steuerelement kennen, wenn die Eigenschaften des Schriftartobjekts geändert wurden. Jedes Schriftartobjekt ist in der Lage, für die Bereitstellung von Benachrichtigungen, wenn er durch den Aufruf einer Memberfunktion ändert die `IFontNotification` von implementierte Schnittstelle `COleControl`.

Wenn das Steuerelement die vordefinierte Schriftarteigenschaft verwendet wird, werden von Benachrichtigungen behandelt die `OnFontChanged` Memberfunktion `COleControl`. Wenn Sie die Eigenschaften für benutzerdefinierte Schriftart hinzufügen, haben Sie diese dieselbe Implementierung verwenden. Im Beispiel im vorherigen Abschnitt zu diesem Zweck übergeben &*M_xFontNotification* beim Initialisieren der *M_fontHeading* Membervariablen gespeichert.

![Implementieren mehrerer Schnittstellen für Schriftartobjekte](../mfc/media/vc373q1.gif "Implementieren mehrerer Schnittstellen für Schriftartobjekte") <br/>
Implementieren mehrerer Schnittstellen für Schriftartobjekte

Die durchgezogene Linien in der obigen Abbildung zeigen, dass beide Schriftartobjekte dieselbe Implementierung von verwenden `IFontNotification`. Dies kann Probleme verursachen, wenn Sie zu unterscheiden, welche Schriftart geändert wurde.

Eine Möglichkeit zur Unterscheidung zwischen des Steuerelements Schriftart Objekt Benachrichtigungen erstellen Sie eine separate Implementierung von ist das `IFontNotification` Schnittstelle für jedes Schriftartobjekt im Steuerelement. Dieses Verfahren können Sie Ihre Zeichencode optimieren, indem Sie aktualisieren nur der Zeichenfolge oder Zeichenfolgen, die die zuletzt geänderte Schriftart zu verwenden. Die folgenden Abschnitte zeigen die erforderlichen Schritte zum gesonderte Benachrichtigung Schnittstellen für eine zweite Font-Eigenschaft. Die zweite Font-Eigenschaft wird als die `HeadingFont` -Eigenschaft, die im vorherigen Abschnitt hinzugefügt wurde.

###  <a name="_core_implementing_a_new_font_notification_interface"></a> Implementieren eine neue Benachrichtigungsschnittstelle

Um die Benachrichtigungen von zwei oder mehr Schriftarten unterscheiden zu können, muss eine neue Benachrichtigungsschnittstelle für jede im Steuerelement verwendete Schriftart implementiert werden. In den folgenden Abschnitten wird beschrieben, wie eine neue Schriftart-Notification-Schnittstelle implementieren, durch Ändern der Header- und Implementierungsdateien Dateien.

### <a name="additions-to-the-header-file"></a>Hinzufügen der Headerdatei

In der Steuerelement-Headerdatei (. H), fügen Sie der Klassendeklaration die folgenden Zeilen hinzu:

[!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]

Dadurch wird eine Implementierung von erstellt die `IPropertyNotifySink` Schnittstelle mit dem Namen `HeadingFontNotify`. Diese neue Schnittstelle enthält eine Methode namens `OnChanged`.

### <a name="additions-to-the-implementation-file"></a>Erweiterungen der Implementierungsdatei

Ändern Sie im Code, der die Schriftart der Überschrift (im Konstruktor Steuerelements) initialisiert, &*M_xFontNotification* zu &*M_xHeadingFontNotify*. Fügen Sie dann den folgenden Code hinzu:

[!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]

Die `AddRef` und `Release` Methoden in der `IPropertyNotifySink` Schnittstelle mitverfolgen den Verweiszähler für das ActiveX-Steuerelement-Objekt. Wenn das Steuerelement den Zugriff auf den Schnittstellenzeiger abruft, ruft das Steuerelement `AddRef` den Verweiszähler inkrementiert werden soll. Wenn das Steuerelement mit dem Mauszeiger abgeschlossen ist, ruft er `Release`, auf ganz ähnliche Weise wie `GlobalFree` kann aufgerufen werden, um einen globalen Speicherblock freigeben. Wenn der Verweiszähler für diese Schnittstelle auf Null geht, kann die Implementierung des freigegeben werden. In diesem Beispiel die `QueryInterface` Funktion gibt einen Zeiger auf eine `IPropertyNotifySink` Schnittstelle für ein bestimmtes Objekt. Diese Funktion ermöglicht, ein ActiveX-Steuerelement zum Abfragen eines Objekts, um zu bestimmen, welche Schnittstellen es unterstützt wird.

Nachdem diese Änderungen zu Ihrem Projekt vorgenommen wurden, wird erstellen Sie das Projekt neu, und verwenden Sie Testcontainer, um die Schnittstelle getestet. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) .

## <a name="see-also"></a>Siehe auch

[MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)<br/>
[MFC-ActiveX-Steuerelemente: Verwenden von Bildern in einem ActiveX-Steuerelement](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)<br/>
[MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)

