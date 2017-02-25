---
title: "MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OnFontChanged"
  - "HeadingFont"
  - "InternalFont"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Schriftarten, ActiveX-Steuerelemente"
  - "GetFont-Methode"
  - "HeadingFont-Eigenschaft"
  - "InternalFont-Methode"
  - "IPropertyNotifySink-Klasse"
  - "MFC-ActiveX-Steuerelemente, Schriftarten"
  - "Benachrichtigungen, MFC ActiveX-Steuerelementeschriftarten"
  - "OnDraw-Methode, MFC-ActiveX-Steuerelemente"
  - "OnFontChanged-Methode"
  - "SelectStockFont-Methode"
  - "SetFont-Methode"
  - "Stock Font-Eigenschaft"
ms.assetid: 7c51d602-3f5a-481d-84d1-a5d8a3a71761
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# MFC-ActiveX-Steuerelemente: Verwenden von Schriftarten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn die ActiveX\-Steuerelement\-Anzeigen Text, können Sie dem Steuerelementbenutzer ermöglichen, um die Textdarstellung ändern, indem Sie eine Schriftarteigenschaft ändern.  Zeicheneigenschaften werden als Schriftartobjekte implementiert und können zwei Typen aufweisen: Bestand oder Benutzerdefiniert.  Vordefinierte Schriftarteigenschaften sind preimplemented Schriftarteigenschaften, die Sie mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen können.  Benutzerdefinierte Schriftarteigenschaften preimplemented nicht und Steuerelemententwickler bestimmt der das Verhalten und die Verwendung Eigenschaft.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Verwenden vordefinierter Schriftarteigenschaft](#_core_using_the_stock_font_property)  
  
-   [Verwenden benutzerdefinierter Schriftarteigenschaften im Steuerelement](#_core_implementing_a_custom_font_property)  
  
##  <a name="_core_using_the_stock_font_property"></a> Verwenden vordefinierter Schriftarteigenschaft  
 Vordefinierte Schriftarteigenschaften preimplemented durch die [COleControl](../mfc/reference/colecontrol-class.md).  Außerdem ist eine Standardschriftarteigenschaftenseite auch verfügbar und ermöglicht den Benutzern zu verschiedenen Attributen der Änderung des Schriftartobjekts, wie deren Namen, Größe und Format.  
  
 Greifen Sie auf das Schriftartobjekt von [GetFont](../Topic/COleControl::GetFont.md), [SetFont](../Topic/COleControl::SetFont.md) und [InternalGetFont](../Topic/COleControl::InternalGetFont.md)\-Funktionen von `COleControl`.  Der Steuerelementbenutzer greift auf das Schriftartobjekt über die Funktionen `GetFont` und `SetFont` auf die gleiche Weise wie für jede andere Cacheabhängigkeit Get\/Set\-Eigenschaft zu.  Wenn auf den Schriftartobjekt aus ein Steuerelement erforderlich ist, verwenden Sie die `InternalGetFont`\-Funktion.  
  
 Wie unter [MFC\-ActiveX\-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md) erläutert, vordefinierten Eigenschaften hinzuzufügen mit [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md) ist einfach.  Sie wählen die Schriftarteigenschaft aus und der Assistent zum Hinzufügen von Eigenschaften fügt automatisch den vordefinierten Schriftarteintrag in die Dispatchzuordnung des Steuerelements ein.  
  
#### So der vordefinierten Schriftarteigenschaft mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Eigenschaften.  
  
5.  Im Feld **Eigenschaftenname** klicken Sie auf **Schriftart**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften wird die folgende Zeile der Dispatchzuordnung des Steuerelements hinzu, in der Steuerelementklassenimplementierungsdatei:  
  
 [!CODE [NVC_MFC_AxFont#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#1)]  
  
 Darüber hinaus fügt der Assistent zum Hinzufügen von Eigenschaften die folgende Zeile der Steueridl\-datei hinzu:  
  
 [!CODE [NVC_MFC_AxFont#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#2)]  
  
 Die vordefinierte Beschriftungseigenschaft ist ein Beispiel einer Text\-Eigenschaft, die mithilfe vordefinierter Informationen zu Schrifteigenschaften gezeichnet werden kann.  Der vordefinierte Beschriftungseigenschaft dem Steuerelement hinzufügen, werden die Schritte, die ähnlich, die für die vordefinierten Schriftarteigenschaft verwendet werden.  
  
#### So der vordefinierten Beschriftungseigenschaft mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Eigenschaften.  
  
5.  Im Feld **Eigenschaftenname** klicken Sie auf **Beschriftung**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften wird die folgende Zeile der Dispatchzuordnung des Steuerelements hinzu, in der Steuerelementklassenimplementierungsdatei:  
  
 [!CODE [NVC_MFC_AxFont#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#3)]  
  
##  <a name="_core_modifying_the_ondraw_function"></a> Ändern der OnDraw\-Funktion  
 Die Standardimplementierung von `OnDraw` verwendet die Windows\-Systemschriftart für sämtlichen Text, der im Steuerelement angezeigt wird.  Das bedeutet, dass Sie den Code `OnDraw` ändern müssen, indem Sie das Schriftartobjekt in den Gerätekontext auswählen.  Hierzu, rufen Sie [COleControl::SelectStockFont](../Topic/COleControl::SelectStockFont.md) auf und übergeben den Gerätekontext des Steuerelements auf, wie im folgenden Beispiel gezeigt:  
  
 [!CODE [NVC_MFC_AxFont#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#4)]  
  
 Nachdem die `OnDraw`\-Funktion geändert, um das Schriftartobjekt zu verwenden, wird der Text innerhalb des Steuerelements mit Eigenschaften der Schriftarteigenschaft der Bestand des Steuerelements angezeigt.  
  
##  <a name="_core_using_custom_font_properties_in_your_control"></a> Verwenden benutzerdefinierter Schriftarteigenschaften im Steuerelement  
 Neben vordefinierten Schriftarteigenschaft kann das ActiveX\-Steuerelement benutzerdefinierte Schriftarteigenschaften haben.  Um eine benutzerdefinierte Schriftarteigenschaft hinzufügen müssen Sie:  
  
-   Verwenden Sie den Assistenten zum Hinzufügen von Eigenschaften, um die benutzerdefinierte Schriftarteigenschaft zu implementieren.  
  
-   [Verarbeiten von Schriftartbenachrichtigungen](#_core_processing_font_notifications).  
  
-   [Implementieren einer neuen Schriftartbenachrichtigungsschnittstelle](#_core_implementing_a_new_font_notification_interface).  
  
###  <a name="_core_implementing_a_custom_font_property"></a> Implementieren einer benutzerdefinierten Schriftarteigenschaft  
 Um eine benutzerdefinierte Schriftarteigenschaft implementieren dann zu lassen, verwenden Sie den Assistenten zum Hinzufügen von Eigenschaften, um die Eigenschaft hinzuzufügen und Änderungen am Code.  In den folgenden Abschnitten wird beschrieben, wie der benutzerdefinierte `HeadingFont`\-Eigenschaft dem Beispielsteuerelement hinzufügt.  
  
##### So fügen die benutzerdefinierte Schriftarteigenschaft mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Eigenschaften.  
  
5.  Im Feld **Eigenschaftenname** geben Sie einen Namen für die Eigenschaft ein.  In diesem Beispiel verwendet **HeadingFont**.  
  
6.  Für **Implementierungstyp** auf **Get\/Set\-Methoden**.  
  
7.  Im Feld **Eigenschaftentyp** aus **IDispatch\***  für den Typ der Eigenschaft.  
  
8.  Klicken Sie auf **Fertig stellen**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften erstellt den Code, um die benutzerdefinierte `HeadingFont`\-Eigenschaft der `CSampleCtrl`\-Klasse und der SAMPLE.IDL\-Datei hinzuzufügen.  Da `HeadingFont` ein Set\-Eigenschaftentyp Get\/ist, ändert der Assistent zum Hinzufügen von Eigenschaften die Dispatchzuordnung der `CSampleCtrl`\-Klasse, um einen Makroeintrag `DISP_PROPERTY_EX_ID`[DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md) einzuschließen:  
  
 [!CODE [NVC_MFC_AxFont#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#5)]  
  
 Das Makro `DISP_PROPERTY_EX` ordnet den `HeadingFont`\-Eigenschaftennamen mit der entsprechenden `CSampleCtrl`\-Klasse und set\-Methoden, `GetHeadingFont` und `SetHeadingFont` zu.  Der Typ des Eigenschaftswerts wird auch angegeben; in diesem Fall **VT\_FONT**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt auch eine Deklaration in der Steuerheaderdatei hinzu \(.H\) für `GetHeadingFont` und `SetHeadingFont` verwendet wird und fügt ihren Funktionsvorlagen in der Steuerimplementierungsdatei hinzu \(.CPP\):  
  
 [!CODE [NVC_MFC_AxFont#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#6)]  
  
 Schließlich ändert der Assistent zum Hinzufügen von Eigenschaften die Steueridl\-datei, indem ein Eintrag für die `HeadingFont`\-Eigenschaft hinzufügt:  
  
 [!CODE [NVC_MFC_AxFont#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#7)]  
  
### Änderungen dem Steuerelementcode  
 Nachdem Sie der `HeadingFont`\-Eigenschaft zum Steuerelement hinzugefügt haben, müssen Sie einige Änderungen an der Steuerkopfzeile und \-Implementierungsdateien vornehmen, um die neue Eigenschaft vollständig zu unterstützen.  
  
 In der Steuerheaderdatei \(.H\), fügen der folgenden Deklaration einer geschützten Membervariable hinzu:  
  
 [!CODE [NVC_MFC_AxFont#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#8)]  
  
 In der Steuerimplementierungsdatei \(.CPP\), sind folgende:  
  
-   Initialisieren Sie `m_fontHeading` im Steuerkonstruktor.  
  
     [!CODE [NVC_MFC_AxFont#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#9)]  
  
-   Deklarieren Sie eine statische **FONTDESC**\-Struktur, die Standardattribute der Schriftart enthält.  
  
     [!CODE [NVC_MFC_AxFont#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#10)]  
  
-   In der Steuerelement\- `DoPropExchange`\-Memberfunktion fügen Sie einen Aufruf der `PX_Font`\-Funktion hinzu.  Dies stellt Initialisierung und Dauerhaftigkeit für die benutzerdefinierte Schriftarteigenschaft bereit.  
  
     [!CODE [NVC_MFC_AxFont#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#11)]  
  
-   Ende, welches die Steuerelement\- `GetHeadingFont`\-Memberfunktion implementiert.  
  
     [!CODE [NVC_MFC_AxFont#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#12)]  
  
-   Ende, welches die Steuerelement\- `SetHeadingFont`\-Memberfunktion implementiert.  
  
     [!CODE [NVC_MFC_AxFont#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#13)]  
  
-   Ändern Sie die Steuerelement\- `OnDraw`\-Memberfunktion, um eine Variable definieren, um die zuvor ausgewählte Schriftart enthält.  
  
     [!CODE [NVC_MFC_AxFont#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#14)]  
  
-   Ändern Sie die Steuerelement\- `OnDraw`\-Memberfunktion, um sie in den Gerätekontext auszuwählen, indem Sie die folgende Zeile hinzu, wenn die Schriftart verwendet werden soll.  
  
     [!CODE [NVC_MFC_AxFont#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#15)]  
  
-   Ändern Sie die Steuerelement\- `OnDraw`\-Memberfunktion, um die vorherige Schriftart zurück in den Gerätekontext auszuwählen, indem Sie die folgende Zeile hinzu, nachdem die Schriftart verwendet wurde.  
  
     [!CODE [NVC_MFC_AxFont#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#16)]  
  
 Nachdem die benutzerdefinierte Schriftarteigenschaft implementiert wurde, sollte die Standardschriftarteigenschaftenseite implementiert und Steuerbenutzern ermöglichen, um die aktuelle Schriftart des Steuerelements zu ändern.  Um die Eigenschaftenseite ID für die Standardschriftarteigenschaftenseite hinzuzufügen, die folgende Zeile nach dem Makro `BEGIN_PROPPAGEIDS` ein:  
  
 [!CODE [NVC_MFC_AxFont#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#17)]  
  
 Sie müssen den `BEGIN_PROPPAGEIDS` Anzahlparameter des Makros durch eines auch erhöhen.  Die folgende Zeile veranschaulicht dies:  
  
 [!CODE [NVC_MFC_AxFont#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#18)]  
  
 Nachdem diese Änderungen vorgenommen wurden, erstellen Sie das gesamte Projekt neu, die zusätzlichen Funktionen zu enthalten.  
  
###  <a name="_core_processing_font_notifications"></a> Verarbeiten von Schriftart\-Benachrichtigungen  
 In den meisten Fällen muss es, zu wissen, wann die Eigenschaften des Schriftartobjekts geändert wurden.  Jedes Schriftartobjekt ist Bereitstellen von Benachrichtigungen geeignet, wenn es geändert, indem eine Memberfunktion der **IFontNotification** aufruft, Schnittstelle implementiert durch `COleControl`.  
  
 Wenn das Steuerelement die vordefinierte Schriftarteigenschaft verwendet, werden die Benachrichtigungen vom `OnFontChanged`\-Memberfunktion von `COleControl` bearbeitet.  Wenn Sie benutzerdefinierte Schriftarteigenschaften hinzufügen, können Sie sie dieselbe Implementierung verwenden.  In dem Beispiel im vorherigen Abschnitt, wurde dies erreicht, indem **m\_xFontNotification** &übergeben, als, die **m\_fontHeading**\-Membervariable Initialisieren.  
  
 ![Mehrere Schnittstellen für Schriftartobjekte werden implementiert](../mfc/media/vc373q1.png "vc373Q1")  
Implementieren mehrerer Schnittstellen für Schriftartobjekte  
  
 Die durchgezogenen Linien in der Abbildung oben geben an, dass beide Schriftartobjekte dieselbe Implementierung von **IFontNotification**.  Dies kann Probleme verursachen, wenn Sie unterscheiden möchten, das sich Schriftart geändert hat.  
  
 Eine Möglichkeit, zwischen den Schriftartobjektbenachrichtigungen des Steuerelements unterscheiden ist, eine separate Implementierung der Schnittstelle **IFontNotification** für jedes Schriftartobjekt im Steuerelement zu erstellen.  Diese Technik lässt Sie, um den Zeichencode, indem nur die Zeichenfolge zu optimieren aktualisiert, oder Zeichenfolgen, die die zuletzt geänderten Schriftart verwenden.  Die folgenden Abschnitte zeigen die Schritte, die erforderlich sind, separate Benachrichtigungsschnittstellen für eine zweite Schriftarteigenschaft zu implementieren.  Die zweite Schriftarteigenschaft wird angenommen, dass die `HeadingFont`\-Eigenschaft sein, die im vorherigen Abschnitt hinzugefügt wurde.  
  
###  <a name="_core_implementing_a_new_font_notification_interface"></a> Implementieren einer neuen Schriftart\-Benachrichtigungs\-Schnittstelle  
 Um zwischen den Benachrichtigungen aus zwei oder mehreren Schriftarten unterscheiden, muss eine neue Benachrichtigungsschnittstelle für alle Schriftarten\- implementiert werden, die im Steuerelement verwendet wird.  In den folgenden Abschnitten wird beschrieben, wie eine neue Schriftartbenachrichtigungsschnittstelle implementiert, indem die Steuerkopfzeile und \-Implementierungsdateien ändern.  
  
### Hinzufügungen zur Headerdatei  
 In der Steuerheaderdatei \(.H\), fügen den folgenden Zeilen der Klassendeklaration hinzu:  
  
 [!CODE [NVC_MFC_AxFont#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#19)]  
  
 Dadurch wird eine Implementierung der Schnittstelle `IPropertyNotifySink`, die `HeadingFontNotify` genannt wird.  Diese neue Schnittstelle enthält eine Methode, die `OnChanged` genannt wird.  
  
### Erweiterungen der Implementierungsdatei  
 In Code, der die Überschriftsschriftart initialisiert \(im Steuerkonstruktor\), ändern Sie `&m_xFontNotification` in `&m_xHeadingFontNotify`.  Fügen Sie dann den folgenden Code hinzu:  
  
 [!CODE [NVC_MFC_AxFont#20](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxFont#20)]  
  
 Die Methoden `AddRef` und `Release` in der `IPropertyNotifySink`\-Schnittstelle behalten den Verweiszähler für das ActiveX\-Steuerelementobjekt nachverfolgt.  Wenn das Steuerelement z Schnittstellenzeiger Zugriff erhält, ruft das Steuerelement `AddRef` auf, um den Verweiszähler zu erhöhen.  Wenn das Steuerelement mit dem Zeiger beendet wird, wird `Release`, auf fast genauso auf, dass **GlobalFree** möglicherweise aufgerufen wird, um einem globalen Speicherblock freizugeben.  Wenn der Verweiszähler für diese Schnittstelle auf Null geht, kann die Schnittstellenimplementierung freigegeben werden.  In diesem Beispiel gibt die `QueryInterface`\-Funktion einen Zeiger auf eine `IPropertyNotifySink`\-Schnittstelle auf einem bestimmten Objekt zurück.  Diese Funktion ermöglicht einem ActiveX\-Steuerelement, um ein Objekt abzufragen, um zu bestimmen, welche Schnittstellen sie unterstützt.  
  
 Nachdem diese Änderungen am Projekt vorgenommen wurden, erstellen Sie das Projekt neu und verwenden Sie Testcontainer, um die Schnittstelle zu testen.  Informationen zum Zugreifen auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md).  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Verwenden von Bildern in einem ActiveX\-Steuerelement](../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)   
 [MFC\-ActiveX\-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md)