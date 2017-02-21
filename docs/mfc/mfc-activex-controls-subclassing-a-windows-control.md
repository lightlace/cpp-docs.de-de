---
title: "MFC-ActiveX-Steuerelemente: Erstellen einer Fenstersteuerelement-Unterklasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "precreatewindow"
  - "IsSubclassed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoSuperclassPaint-Methode"
  - "IsSubclassed-Methode"
  - "MFC-ActiveX-Steuerelemente, Erstellen"
  - "MFC-ActiveX-Steuerelemente, Steuerelemente als Unterklasse"
  - "OnDraw-Methode, MFC-ActiveX-Steuerelemente"
  - "PreCreateWindow-Methode, Überschreiben"
  - "Reflektierte Meldungen, in ActiveX-Steuerelementen"
  - "Unterklasse erstellen"
  - "Erstellen von Unterklassen für Windows-Steuerelemente"
  - "Unterklasse erstellen, Windows-Steuerelemente"
ms.assetid: 3236d4de-401f-49b7-918d-c84559ecc426
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC-ActiveX-Steuerelemente: Erstellen einer Fenstersteuerelement-Unterklasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel beschreibt den Prozess zum Erstellen von Unterklassen von einem allgemeinen Windows\-Steuerelements, um ein ActiveX\-Steuerelement zu erstellen.  Ein vorhandenes Windows\-Steuerelement unterzuordnen ist eine schnelle Möglichkeit, ein ActiveX\-Steuerelement entwickeln.  Das neue Steuerelement verfügt die Fähigkeiten des Windows\-Steuerelements untergeordneten, wie Zeichnen und Reagieren auf Mausklicks.  Die Kontrollprobe MFC ActiveX [SCHALTFLÄCHE](../top/visual-cpp-samples.md) ist ein Beispiel für Unterordnens eines Windows\-Steuerelements.  
  
 Um ein Windows\-Steuerelement unterzuordnen, führen Sie die folgenden Aufgaben aus:  
  
-   [Überschreiben Sie die Memberfunktionen IsSubclassedControl und PreCreateWindow von COleControl](#_core_overriding_issubclassedcontrol_and_precreatewindow)  
  
-   [Ändern Sie die OnDraw\-Memberfunktion](#_core_modifying_the_ondraw_member_function)  
  
-   [Bearbeiten Sie alle ActiveX\-Steuerelement\-Meldungen \(OCM\) übermittelt an das Steuerelement](#_core_handling_reflected_window_messages)  
  
    > [!NOTE]
    >  Ein Großteil dieser Arbeit wird für Sie im ActiveX\-Steuerelement\-Assistenten ausgegeben, wenn Sie das mit aus der Dropdownliste **Übergeordnete Fensterklasse auswählen** auf der Seite **Steuerelementeinstellungen** als Unterklasse definiert werden, Steuerelement.  
  
 finden Sie im Knowledge Base\-Artikel Q243454 zu Informationen zum Erstellen von Unterklassen von einem Steuerelement.  
  
##  <a name="_core_overriding_issubclassedcontrol_and_precreatewindow"></a> Überschreiben von IsSubclassedControl und von PreCreateWindow  
 Um `PreCreateWindow` und `IsSubclassedControl` zu überschreiben, fügen Sie die folgenden Codezeilen im Abschnitt `protected` der Steuerelementklassendeklaration hinzu:  
  
 [!CODE [NVC_MFC_AxSub#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#1)]  
  
 In der Steuerimplementierungsdatei \(.CPP\), fügen Sie die folgenden Codezeilen hinzu, um die zwei überschriebenen Funktionen zu implementieren:  
  
 [!CODE [NVC_MFC_AxSub#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#2)]  
  
 Beachten Sie, dass, in diesem Beispiel, das Schaltflächen\-Steuerelement von Windows in `PreCreateWindow` angegeben wird.  Sie können jedoch alle Standardwindows\-steuerelemente als Unterklasse definiert werden.  Weitere Informationen über Standardwindows\-steuerelemente, finden Sie unter [Steuerelemente](../mfc/controls-mfc.md).  
  
 Wenn Sie ein Windows\-Steuerelement, können Sie bestimmten Fensterstil \(**WS\_** angeben möchten unterordnen oder erweiterter Fensterstil \(**WS\_EX\_**\) kennzeichnet, verwendet werden, wenn das Fenster des Steuerelements erstellt.  Sie können die Werte für diese Parameter in der Memberfunktion `PreCreateWindow`, indem Sie **cs.style** und die **cs.dwExStyle**\-Strukturfelder ändern.  Änderungen an diesen Feldern sollten unter Verwendung eines `OR` \- Vorgangs erstellt werden, um die Standardflags beizubehalten, die durch `COleControl`\- Klasse festgelegt werden.  Wenn das Steuerelement das Schaltflächen\-Steuerelement als Unterklasse festlegt und Sie das Steuerelement als Kontrollkästchen angezeigt werden soll, die folgende Codezeile in die Implementierung von `CSampleCtrl::PreCreateWindow`, vor der return\-Anweisung ein:  
  
 [!CODE [NVC_MFC_AxSub#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#3)]  
  
 Dieser Vorgang fügt das **BS\_CHECKBOX** Formatflag hinzu, während die Deckkraft des Standardstilflags \(**WS\_CHILD**\) der `COleControl`\-Klasse erhalten.  
  
##  <a name="_core_modifying_the_ondraw_member_function"></a> Ändern der OnDraw\-Memberfunktion  
 Wenn Sie ein untergeordnetes Steuerelement die gleiche Darstellung wie das entsprechende Windows\-Steuerelement halten möchten, sollte die Memberfunktion `OnDraw` für das Steuerelement nur einen Aufruf der Memberfunktion `DoSuperclassPaint`, wie im folgenden Beispiel enthalten:  
  
 [!CODE [NVC_MFC_AxSub#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#4)]  
  
 Die Memberfunktion `DoSuperclassPaint`, implementiert durch `COleControl`, verwendet die Fensterprozedur des Windows\-Steuerelements, um das Steuerelement im angegebenen Gerätekontext, innerhalb des umgebenden Rechtecks zu zeichnen.  Dadurch wird das Steuerelement angezeigt erstellt, wenn es nicht aktiv ist.  
  
> [!NOTE]
>  Die Memberfunktion `DoSuperclassPaint` funktioniert nur mit diesen Steuerelementtypen, die einen als **wParam** ermöglichen eine `WM_PAINT` Meldung übergeben werden Gerätekontext.  Dies schließt einige der Standardwindows\-steuerelemente, wie **BILDLAUFLEISTE** und **SCHALTFLÄCHE** alle gängigen Steuerelementen ein.  Für Steuerelemente, die dieses Verhalten nicht unterstützen, müssen Sie einen eigenen Code bereitstellen, um ein Steuerelement ordnungsgemäß Präprozessordirektiven anzuzeigen.  
  
##  <a name="_core_handling_reflected_window_messages"></a> Behandeln von Fenster\-Meldungen reflektierten  
 Windows\-Steuerelemente senden in der Regel bestimmte Fenstermeldungen zum übergeordneten Fenster.  Einige dieser Meldungen, wie **WM\_COMMAND**, erstellen Benachrichtigung über eine Aktion vom Benutzer.  Andere, wie `WM_CTLCOLOR`, werden verwendet, um Informationen im übergeordneten Fenster abzurufen.  Ein ActiveX\-Steuerelement ist normalerweise das übergeordnete Fenster durch andere Mittel kommunizieren.  Benachrichtigungen werden übermittelt, indem die Ereignisse \(Ereignisbenachrichtigungen zu senden\) auslöst, und Informationen über den Steuerelementcontainer werden abgerufen, indem mit der Ambient\-Eigenschaften des Containers zugreift.  Da diese Kommunikationstechniken bestehen, werden ActiveX\-Steuerelementcontainer erwartet, keine Fenstermeldungen zu verarbeiten, die das Steuerelement sendet werden.  
  
 Um zu verhindern dass der Container die Fenstermeldungen empfängt, die ein untergeordnetes Windows\-Steuerelement `COleControl` gesendet werden, wird ein zusätzliches Fenster das als das übergeordnete Element des Steuerelements verwendet werden.  Auf zusätzliche Fenster, einen Reflektor aufgerufen "," wird nur für ein ActiveX\-Steuerelement erstellt, der ein Windows\-Steuerelement als Unterklasse festlegt und die gleiche Größe und die Position als das Steuerfenster hat.  Die Reflektorfensterabfangbestimmten Fenstermeldungen und sendet sie zurück zum Steuerelement.  Das Steuerelement, in der Fensterprozedur, kann diese reflektierten Meldungen dann verarbeiten, indem die Aktion durchführt, die für ein ActiveX\-Steuerelement entsprechen \(beispielsweise, ein Ereignis auszulösen\).  [Reflektierte Fenster\-Meldungs\-IDs](../mfc/reflected-window-message-ids.md) finden Sie eine Liste der abgefangenen Fenstermeldungen und ihrer entsprechenden reflektierten Meldungen.  
  
 Ein ActiveX\-Steuerelementcontainer ist entworfen werden, um Meldungsreflektion selbst auszuführen, entfällt die Notwendigkeit, damit `COleControl` das Reflektorfenster erstellt und reduziert den Aufwand zur Laufzeit für ein untergeordnetes Windows\-Steuerelement.  `COleControl` erkennt, dass der Container die Funktion unterstützt wird, indem er für eine MessageReflect\-Ambient\-Eigenschaft mit einem Wert **TRUE** überprüft.  
  
 Um eine reflektierte Fenstermeldung bearbeiten, fügen Sie einen Eintrag der Steuerelementmeldungszuordnung hinzu und implementieren Sie eine Handlerfunktion.  Da reflektierte Meldungen nicht Teil des Standardsatzes der Meldungen sind, die von Windows definiert werden, unterstützt Klassenansicht nicht das Hinzufügen solcher Meldungshandler.  Es ist jedoch nicht schwierig, einen Handler manuell hinzuzufügen.  
  
 Um einen Meldungshandler für eine reflektierte Fenstermeldung manuell hinzuzufügen führen Sie Folgendes:  
  
-   In der Steuerelementklasse. H\-Datei, deklarieren eine Handlerfunktion.  Die Funktion sollte einen Rückgabetyp und **LRESULT** zwei Parameter, mit Typen **WPARAM** und **LPARAM** verfügen, bzw.  Beispiel:  
  
     [!CODE [NVC_MFC_AxSub#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#5)]  
    [!CODE [NVC_MFC_AxSub#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#6)]  
  
-   In der Steuerelementklassencpp\-datei fügen Sie einen Eintrag der Meldungszuordnung `ON_MESSAGE` hinzu.  Die Parameter dieses Eintrags sollten die Nachricht und der Name der Handlerfunktion sein.  Beispiel:  
  
     [!CODE [NVC_MFC_AxSub#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSub#7)]  
  
-   Auch in der CPP\-Datei, implementieren die **OnOcmCommand**\-Memberfunktion, um die reflektierte Meldung zu verarbeiten.  Die **wParam** und **lParam**\-Parameter sind mit denen identisch der ursprünglichen Fenstermeldung.  
  
 Ein Beispiel, wie reflektierte Meldungen verarbeitet werden, können Sie die Kontrollprobe MFC ActiveX [SCHALTFLÄCHE](../top/visual-cpp-samples.md).  Es zeigt einen Handler, den **OnOcmCommand** der **BN\_CLICKED** Benachrichtigungscode erkennt und reagiert, indem es \(Senden\) ein Klickereignis ausgelöst.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)