---
title: 'MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- OnFontChanged
- HeadingFont
- InternalFont
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b53ab98e44a8696795e810b8d6f643720d8f9655
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355138"
---
# <a name="mfc-activex-controls-using-fonts"></a>MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten
Wenn das ActiveX-Steuerelement Text angezeigt wird, können Sie die Benutzer des Steuerelements die Textdarstellung zu ändern, indem Sie eine Schriftarteigenschaft. Schriftarteigenschaften werden als Schriftartobjekte implementiert und kann einen von zwei Typen: vordefinierte oder benutzerdefinierte. Basiseigenschaften Schriftart sind bereits Eigenschaften, die Sie hinzufügen können, verwenden den Assistenten zum Hinzufügen einer Eigenschaft an. Benutzerdefinierte Schriftart-Eigenschaften sind nicht vorimplementiert und Steuerelemententwickler bestimmt werden, Verhalten und die Verwendung der Eigenschaft.  
  
 In diesem Artikel werden die folgenden Themen behandelt:  
  
-   [Mithilfe der Stock Font-Eigenschaft](#_core_using_the_stock_font_property)  
  
-   [Verwenden benutzerdefinierte Schriftart-Eigenschaften in das Steuerelement](#_core_implementing_a_custom_font_property)  
  
##  <a name="_core_using_the_stock_font_property"></a> Verwenden die vordefinierte Schriftarteigenschaft  
 Stock Font-Eigenschaften werden von der Klasse vorimplementiert [COleControl](../mfc/reference/colecontrol-class.md). Darüber hinaus wird eine standardmäßige Schriftart-Eigenschaftenseite auch zur Verfügung haben und des Benutzers verschiedene Attribute des Schriftartobjekts, z. B. Name, Größe und Format ändern.  
  
 Greifen Sie auf die Schriftartobjekt über die [GetFont](../mfc/reference/colecontrol-class.md#getfont), [SetFont](../mfc/reference/colecontrol-class.md#setfont), und [InternalGetFont](../mfc/reference/colecontrol-class.md#internalgetfont) Funktionen `COleControl`. Der Benutzer des Steuerelements greifen auf das Font-Objekt über die `GetFont` und `SetFont` Funktionen in die gleiche Weise wie jede andere Get/Set-Eigenschaft. Beim Zugriff auf das Font-Objekt in einem Steuerelement vom erforderlich ist, verwenden die `InternalGetFont` Funktion.  
  
 Entsprechend der Anleitung unter [MFC-ActiveX-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md), Hinzufügen von vordefinierten Eigenschaften ist einfach mit der [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md). Sie wählen die Schriftarteigenschaft und der Assistent zum Hinzufügen von Eigenschaften fügt automatisch den stock Font-Eintrag in die Dispatchzuordnung des Steuerelements.  
  
#### <a name="to-add-the-stock-font-property-using-the-add-property-wizard"></a>So fügen Sie die vordefinierte Schriftarteigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzu  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Dies öffnet den Assistenten zum Hinzufügen einer Eigenschaft.  
  
5.  In der **Eigenschaftsname** auf **Schriftart**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften hinzugefügt des Steuerelements Dispatchzuordnung in der Implementierungsdatei des Steuerelements-Klasse die folgende Zeile:  
  
 [!code-cpp[NVC_MFC_AxFont#1](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_1.cpp)]  
  
 Darüber hinaus fügt der Assistent zum Hinzufügen von Eigenschaften die folgende Zeile auf das Steuerelement. IDL-Datei:  
  
 [!code-cpp[NVC_MFC_AxFont#2](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_2.idl)]  
  
 Die vordefinierte Caption-Eigenschaft ist ein Beispiel für eine Texteigenschaft, die mit den vordefinierten Eigenschaft Schriftartinformationen gezeichnet werden kann. Hinzufügen den Bestand Caption-Eigenschaft zum Steuerelement verwendet die Schritte, die ähnlich wie für die Stock Font-Eigenschaft.  
  
#### <a name="to-add-the-stock-caption-property-using-the-add-property-wizard"></a>Hinzufügen von vordefinierten Caption-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Dies öffnet den Assistenten zum Hinzufügen einer Eigenschaft.  
  
5.  In der **Eigenschaftsname** auf **Beschriftung**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften hinzugefügt des Steuerelements Dispatchzuordnung in der Implementierungsdatei des Steuerelements-Klasse die folgende Zeile:  
  
 [!code-cpp[NVC_MFC_AxFont#3](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_3.cpp)]  
  
##  <a name="_core_modifying_the_ondraw_function"></a> Ändern die OnDraw-Funktion  
 Die standardmäßige Implementierung des `OnDraw` verwendet die Windows-System-Schriftart für den gesamten Text im Steuerelement angezeigt. Dies bedeutet, dass ändern, müssen Sie die `OnDraw` Code durch das Font-Objekt in den Gerätekontext auswählen. Zu diesem Zweck rufen [COleControl:: SelectStockFont](../mfc/reference/colecontrol-class.md#selectstockfont) und Gerätekontext, für das Steuerelement übergeben, wie im folgenden Beispiel gezeigt:  
  
 [!code-cpp[NVC_MFC_AxFont#4](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_4.cpp)]  
  
 Nach der `OnDraw` Funktion wurde geändert, um das Font-Objekt verwenden, wird Text im Steuerelement durch die Merkmale des Steuerelements vordefinierte Schriftarteigenschaft angezeigt.  
  
##  <a name="_core_using_custom_font_properties_in_your_control"></a> Verwenden benutzerdefinierte Schriftart-Eigenschaften in das Steuerelement  
 Zusätzlich zu die vordefinierte Schriftarteigenschaft kann das ActiveX-Steuerelement benutzerdefinierte Schriftarteigenschaften haben. Hinzufügen eine benutzerdefinierten Schriftart-Eigenschaft müssen Sie folgende Aktionen ausführen:  
  
-   Verwenden Sie den Assistenten zum Hinzufügen einer Eigenschaft, um die benutzerdefinierte Schriftart-Eigenschaft zu implementieren.  
  
-   [Verarbeitungsmeldungen Schriftart](#_core_processing_font_notifications).  
  
-   [Implementieren eine neue Benachrichtigungsschnittstelle](#_core_implementing_a_new_font_notification_interface).  
  
###  <a name="_core_implementing_a_custom_font_property"></a> Implementieren eine benutzerdefinierte Schriftart-Eigenschaft  
 Um eine benutzerdefinierte Schriftarteigenschaft zu implementieren, verwenden Sie den Assistenten zum Hinzufügen einer Eigenschaft die Eigenschaft hinzugefügt, und klicken Sie dann einige Änderungen am Code vornehmen. In den folgenden Abschnitten wird beschrieben, wie Sie die benutzerdefinierte hinzufügen- `HeadingFont` -Eigenschaft können Sie das Beispiel steuern.  
  
##### <a name="to-add-the-custom-font-property-using-the-add-property-wizard"></a>So fügen Sie die benutzerdefinierte Schriftart-Eigenschaft, die mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzu  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements (den zweiten Knoten des Bibliotheksknotens), um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Eigenschaft hinzufügen**.  
  
     Dies öffnet den Assistenten zum Hinzufügen einer Eigenschaft.  
  
5.  In der **Eigenschaftsname** geben einen Namen für die Eigenschaft. Verwenden Sie für dieses Beispiel **HeadingFont**.  
  
6.  Klicken Sie unter **Implementierungstyp**auf **Get/Set-Methoden**.  
  
7.  In der **Eigenschaftentyp** wählen Sie im **IDispatch\***  für den Typ der Eigenschaft.  
  
8.  Klicken Sie auf **Fertig stellen**.  
  
 Den Assistenten zum Hinzufügen, erstellt den Code zum Hinzufügen der `HeadingFont` benutzerdefinierte Eigenschaft, um die `CSampleCtrl` Klasse und das Beispiel. IDL-Datei. Da `HeadingFont` ist ein Get/Set-Eigenschaft, den Assistenten zum Hinzufügen einer Eigenschaft ändert die `CSampleCtrl` Klasse Dispatchzuordnung einschließen einer `DISP_PROPERTY_EX_ID` [DISP_PROPERTY_EX](../mfc/reference/dispatch-maps.md#disp_property_ex) Makro-Eintrag:  
  
 [!code-cpp[NVC_MFC_AxFont#5](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_5.cpp)]  
  
 Die `DISP_PROPERTY_EX` Makro ordnet die `HeadingFont` Eigenschaftennamen und die entsprechenden `CSampleCtrl` Klasse abrufen und Festlegen von Methoden, `GetHeadingFont` und `SetHeadingFont`. Der Typ des Eigenschaftswerts ist ebenfalls angegeben; In diesem Fall **VT_FONT**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt eine Deklaration auch in der Headerdatei des Steuerelements (. H) für die `GetHeadingFont` und `SetHeadingFont` Funktionen und fügt deren Funktionsvorlagen in der Implementierungsdatei des Steuerelements (. CPP):  
  
 [!code-cpp[NVC_MFC_AxFont#6](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_6.cpp)]  
  
 Schließlich ändert der Assistent zum Hinzufügen von Eigenschaften des Steuerelements. IDL-Datei, indem Sie ein Eintrag für die `HeadingFont` Eigenschaft:  
  
 [!code-cpp[NVC_MFC_AxFont#7](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_7.idl)]  
  
### <a name="modifications-to-the-control-code"></a>Änderungen an der Steuerungscode  
 Nun, dass Sie hinzugefügt haben, die `HeadingFont` -Eigenschaft für das Steuerelement, müssen Sie einige Änderungen vornehmen, auf die Steuerelement-Header und die Implementierung-Dateien, um die neue Eigenschaft vollständig zu unterstützen.  
  
 In der Steuerelement-Headerdatei (. H), fügen Sie die folgende Deklaration einer geschützten Membervariablen hinzu:  
  
 [!code-cpp[NVC_MFC_AxFont#8](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_8.h)]  
  
 In der Implementierungsdatei des Steuerelements (. CPP), gehen Sie folgendermaßen vor:  
  
-   Initialisieren `m_fontHeading` im Konstruktor Steuerelements.  
  
     [!code-cpp[NVC_MFC_AxFont#9](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_9.cpp)]  
  
-   Deklarieren Sie einen statischen **FONTDESC** Struktur, die Standardattribute der Schriftart enthält.  
  
     [!code-cpp[NVC_MFC_AxFont#10](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_10.cpp)]  
  
-   Im Steuerelement `DoPropExchange` Member-Funktion, fügen Sie einen Aufruf der `PX_Font` Funktion. Dies führt Initialisierung und Persistenz für die benutzerdefinierte Schriftart-Eigenschaft.  
  
     [!code-cpp[NVC_MFC_AxFont#11](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_11.cpp)]  
  
-   Schließen Sie die Implementierung des Steuerelements `GetHeadingFont` Memberfunktion.  
  
     [!code-cpp[NVC_MFC_AxFont#12](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_12.cpp)]  
  
-   Schließen Sie die Implementierung des Steuerelements `SetHeadingFont` Memberfunktion.  
  
     [!code-cpp[NVC_MFC_AxFont#13](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_13.cpp)]  
  
-   Ändern Sie das Steuerelement `OnDraw` Memberfunktion versucht, eine Variable, um die zuvor ausgewählte Schriftart zu definieren.  
  
     [!code-cpp[NVC_MFC_AxFont#14](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_14.cpp)]  
  
-   Ändern Sie das Steuerelement `OnDraw` Memberfunktion versucht, wählen Sie die benutzerdefinierte Schriftart in den Gerätekontext durch Hinzufügen der folgenden Zeile, wo die Schriftart verwendet wird.  
  
     [!code-cpp[NVC_MFC_AxFont#15](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_15.cpp)]  
  
-   Ändern Sie das Steuerelement `OnDraw` Memberfunktion versucht, wählen Sie die vorherige Schriftart wieder für den Gerätekontext, indem Sie die folgende Zeile hinzufügen, nachdem die Schriftart verwendet wurde.  
  
     [!code-cpp[NVC_MFC_AxFont#16](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_16.cpp)]  
  
 Nachdem die benutzerdefinierte Schriftarteigenschaft implementiert wurde, sollte die standard Schriftart-Eigenschaftenseite implementiert werden, wodurch Steuerelementbenutzer so ändern Sie die aktuelle Schriftart für das Steuerelement. Um die Eigenschaftenseiten-ID für die standardmäßige Schriftart-Eigenschaftenseite hinzuzufügen, fügen Sie die folgende Zeile nach der `BEGIN_PROPPAGEIDS` Makro:  
  
 [!code-cpp[NVC_MFC_AxFont#17](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_17.cpp)]  
  
 Zusätzlich muss der Zählparameter des `BEGIN_PROPPAGEIDS` -Makros um den Wert 1 erhöht werden. Die folgende Zeile veranschaulicht dies:  
  
 [!code-cpp[NVC_MFC_AxFont#18](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_18.cpp)]  
  
 Nachdem diese Änderungen vorgenommen wurden, neu erstellen Sie das gesamte Projekt aus, um die zusätzliche Funktionalität zu integrieren.  
  
###  <a name="_core_processing_font_notifications"></a> Schriftart verarbeitungsmeldungen  
 In den meisten Fällen muss das Steuerelement kennen, wenn die Merkmale des Schriftartobjekts geändert wurden. Jedes Schriftartobjekt ist Benachrichtigungen bereitstellen, durch den Aufruf einer Memberfunktion ändert die **IFontNotification** von implementierte Schnittstelle `COleControl`.  
  
 Wenn das Steuerelement die vordefinierte Schriftarteigenschaft verwendet wird, werden die Benachrichtigungen vom verarbeitet die `OnFontChanged` Memberfunktion von `COleControl`. Wenn Sie benutzerdefinierte Schriftarteigenschaften hinzufügen, können Sie sie der dieselbe Implementierung verwenden lassen. Im Beispiel im vorherigen Abschnitt zu diesem Zweck übergeben &**M_xFontNotification** beim Initialisieren der **M_fontHeading** Membervariablen gespeichert.  
  
 ![Implementieren mehrerer Schnittstellen für Schriftartobjekte](../mfc/media/vc373q1.gif "vc373q1")  
Implementieren mehrerer Schnittstellen für Schriftartobjekte  
  
 Die Durchgezogen Linien in der obigen Abbildung zeigen, dass beide Schriftartobjekte dieselbe Implementierung von verwenden **IFontNotification**. Dies kann Probleme verursachen, wenn Sie zu unterscheiden, welche Schriftart geändert.  
  
 Eine Möglichkeit zur Unterscheidung zwischen den Benachrichtigungen für das Steuerelement Schriftart-Objekt ist die Erstellung eine separate Implementierung von der **IFontNotification** Schnittstelle für jedes Schriftartobjekt im Steuerelement. Bei dieser Technik können Sie zeichnen Code optimieren, indem Sie aktualisieren nur die Zeichenfolge oder Zeichenfolgen, die die zuletzt geänderte Schriftart verwenden. Die folgenden Abschnitte zeigen die erforderlichen Schritte zum Implementieren verschiedener Benachrichtigungsschnittstellen für eine zweite Font-Eigenschaft. Die zweite Schriftarteigenschaft wird angenommen werden, dass die `HeadingFont` -Eigenschaft, die im vorherigen Abschnitt hinzugefügt wurde.  
  
###  <a name="_core_implementing_a_new_font_notification_interface"></a> Implementieren eine neue Benachrichtigungsschnittstelle  
 Um die Benachrichtigungen von zwei oder mehr Schriftarten unterscheiden zu können, muss eine neue Benachrichtigung-Schnittstelle für jede im Steuerelement verwendete Schriftart implementiert werden. In den folgenden Abschnitten wird beschrieben, wie so implementieren Sie eine neue Benachrichtigungsschnittstelle Steuerungsdateien Header und die Implementierung zu ändern.  
  
### <a name="additions-to-the-header-file"></a>Hinzufügen der Headerdatei  
 In der Steuerelement-Headerdatei (. H), fügen Sie der Klassendeklaration die folgenden Zeilen hinzu:  
  
 [!code-cpp[NVC_MFC_AxFont#19](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_19.h)]  
  
 Dadurch wird eine Implementierung von erstellt die `IPropertyNotifySink` Schnittstelle mit dem Namen `HeadingFontNotify`. Diese neue Schnittstelle enthält eine Methode namens `OnChanged`.  
  
### <a name="additions-to-the-implementation-file"></a>Ergänzungen der Implementierungsdatei  
 Ändern Sie im Code, der die Überschriftenschriftart (im Konstruktor Steuerelements) initialisiert, `&m_xFontNotification` auf `&m_xHeadingFontNotify`. Fügen Sie dann den folgenden Code hinzu:  
  
 [!code-cpp[NVC_MFC_AxFont#20](../mfc/codesnippet/cpp/mfc-activex-controls-using-fonts_20.cpp)]  
  
 Die `AddRef` und `Release` Methoden in der `IPropertyNotifySink` Schnittstelle Nachverfolgen von den Verweiszähler für das ActiveX-Steuerelementobjekt. Wenn das Steuerelement den Zugriff auf den Schnittstellenzeiger erhält, ruft das Steuerelement `AddRef` inkrementiert den Verweiszähler dieser Planergruppe. Wenn das Steuerelement mit dem Zeiger abgeschlossen ist, ruft er `Release`, ähnlich wie **GlobalFree** aufgerufen werden kann, um einen globalen Speicherblock freigeben. Wenn der Verweiszähler für diese Schnittstelle 0 (null) ist, kann die Implementierung freigegeben werden. In diesem Beispiel wird die `QueryInterface` Funktion gibt einen Zeiger auf eine `IPropertyNotifySink` Schnittstelle für ein bestimmtes Objekt. Diese Funktion ermöglicht es, ein ActiveX-Steuerelement die Abfrage eines Objekts, um zu bestimmen, welche Schnittstellen es unterstützt.  
  
 Nach dem Projekt diese Änderungen vorgenommen wurden, wird das Projekt neu, und verwenden Sie Testcontainer, um die Schnittstelle getestet. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) .  
  
## <a name="see-also"></a>Siehe auch  
 [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC-ActiveX-Steuerelemente: Verwenden von Bildern in einem ActiveX-Steuerelement](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)   
 [MFC-ActiveX-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)

