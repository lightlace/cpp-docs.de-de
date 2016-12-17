---
title: "Aktualisieren des Textes in der Statusleiste"
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
  - "CStatusBar-Klasse, Aktualisieren"
  - "ON_UPDATE_COMMAND_UI-Makro"
  - "Bereiche, Statusleiste"
  - "SetText-Methode"
  - "Statusleisten, Aktualisieren"
  - "Text, Statusleiste"
  - "Aktualisieren von Benutzeroberflächenobjekten"
  - "Benutzerschnittstellenobjekte, Aktualisieren"
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Aktualisieren des Textes in der Statusleiste
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird beschrieben, wie der Text ändert, der in einem MFC\-Statusleistenbereich wird.  Eine \- Statusleiste ein Window\-Objekt der Klasse [CStatusBar](../mfc/reference/cstatusbar-class.md) \- Enthält verschiedene "Bereiche". Jeder Bereich ist ein rechteckiger Bereich der Statusleiste, die Sie verwenden können, um Informationen anzuzeigen.  Beispielsweise zeigen viele Anwendungen den Status der FESTSTELLTASTE, des NUMs und anderer Schlüssel in den am weitesten rechts befindlichen Bereichen angezeigt.  Anwendungen auch zeigen oft Informationskomponenten Text im linken Bereich \(Bereich 0\), den Meldungsbereich gelegentlich aufgerufen "." Beispielsweise verwendet die Statusleiste des Standardanbieters MFC den Meldungsbereich, um eine Zeichenfolge anzuzeigen, die das gerade ausgewählte Menüelement oder die Symbolleistenschaltfläche erläutert.  Die Abbildung in [Statusleisten](../mfc/status-bar-implementation-in-mfc.md) wird eine Statusleiste von einer Anwendung Assistent\-erstellten MFC\-Anwendung an.  
  
 Standardmäßig aktiviert MFC keinen Bereich `CStatusBar`, wenn sie den Bereich erstellt.  Um einen Bereich zu aktivieren, müssen Sie das `ON_UPDATE_COMMAND_UI`\-Makro für jeden Bereich der Statusleiste verwenden und Bereiche aktualisiert.  Da Bereiche nicht **WM\_COMMAND** Meldungen \(nicht z Symbolleisten\-Schaltflächen\), Senden, müssen Sie den Code manuell eingeben.  
  
 Angenommen, ein Bereich `ID_INDICATOR_PAGE` als Befehlskennzeichen verfügt und dem er die aktuelle Seitenzahl in einem Dokument enthält.  Die folgende Prozedur beschreibt, wie Sie einen neuen Bereich in der Statusleiste.  
  
### Um einen neuen Bereich erstellen  
  
1.  Definieren Sie ID der Befehl des Bereichs  
  
     Klicken Sie im Menü **Ansicht**  auf **Ressourcenansicht**.  Klicken Sie auf die Projektressource mit der rechten Maustaste auf **Ressourcensymbole**.  Im Ressourcen\-Symboldialogfeld klicken Sie auf `New`.  Geben Sie einen Befehls\-ID\-Namen ein: beispielsweise `ID_INDICATOR_PAGE`.  Geben Sie einen Wert für die ID, oder übernehmen Sie den Wert, der vom Ressourcen\-Symboldialogfeld vorgeschlagen wird.  Für `ID_INDICATOR_PAGE`, übernehmen Sie den Standardwert.  Schließen Sie das Ressourcen\-Symboldialogfeld.  
  
2.  Definieren einer Standardzeichenfolge, im Bereich anzuzeigen.  
  
     Mit der Ressourcenansicht geöffnet, doppelklicken Sie im Fenster **Zeichenfolgentabelle** Ressourcentypen, das für die Anwendung enthält.  geöffnetem **Zeichenfolgentabelle** Editor, wählen Sie **Neue Zeichenfolge** im Menü **Einfügen**  aus.  Im Zeichenfolgen\-Eigenschaftenfenster wählen Sie die Befehls\-ID des Panels \(beispielsweise, `ID_INDICATOR_PAGE`\) aus und geben Sie einen Standard\-Zeichenfolgenwert, wie "Seite" ein.  Schließen Sie den Editor. \(Sie benötigen eine Standardzeichenfolge, um einen Compilerfehler zu vermeiden.\)  
  
3.  Fügen Sie dem Bereich dem Array **Indikatoren** hinzu.  
  
     In der Datei MAINFRM.CPP, suchen Sie das **Indikatoren** Array.  Dies Matrixlistebefehls\-ids für alle Indikatoren der Statusleiste, in Reihenfolge von links nach rechts.  Am entsprechenden Punkt im Array, geben Sie der Befehls\-ID des Bereichs, wie hier gezeigt für `ID_INDICATOR_PAGE` ein:  
  
     [!CODE [NVC_MFCDocView#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#10)]  
  
 Die empfohlene Methode, Text in einem Bereich anzuzeigen, die **SetText**\-Memberfunktion der `CCmdUI`\-Klasse in einer Aktualisierungshandlerfunktion für den Bereich aufzurufen.  Beispielsweise sollten Sie eine ganzzahlige `m_nPage` installieren, die die aktuelle Seitenzahl und die Verwendung von **SetText**, enthält den Text des Bereichs auf eine Angabe dieser Zahl festzulegen.  
  
> [!NOTE]
>  Der **SetText** ist die empfohlene Vorgehensweise.  Es ist möglich, diese Aufgabe mit einem etwas auf der untersten Ebene auszuführen, indem die `CStatusBar`\-Memberfunktion `SetPaneText` aufruft.  Dennoch müssen jedoch weiterhin einen Aktualisierungshandler.  Ohne einen solchen Handler für den Bereich, deaktiviert MFC automatisch den Bereich und löscht den Inhalt.  
  
 Die folgende Prozedur zeigt, wie eine Aktualisierungshandlerfunktion verwendet, um Text in einem Bereich anzeigen.  
  
#### Um einen Bereich erstellen, Text anzuzeigen  
  
1.  Fügen Sie einem Befehlsaktualisierungshandler für den Befehl hinzu.  
  
     Fügen Sie manuell einen Prototyp für den Handler, wie hier gezeigt für `ID_INDICATOR_PAGE` \(in MAINFRM.H\):  
  
     [!CODE [NVC_MFCDocView#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#11)]  
  
2.  In der entsprechenden CPP\-Datei fügen Sie die Definition des Handlers, wie hier gezeigt für `ID_INDICATOR_PAGE` \(in MAINFRM.CPP\):  
  
     [!CODE [NVC_MFCDocView#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#12)]  
  
     Die letzten drei Zeilen dieser Handler sind der Code, der den Text anzeigt.  
  
3.  In der entsprechenden Meldungszuordnung fügen Sie dem `ON_UPDATE_COMMAND_UI`\-Makro, wie hier gezeigt für `ID_INDICATOR_PAGE` \(in MAINFRM.CPP\):  
  
     [!CODE [NVC_MFCDocView#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#13)]  
  
 Sobald Sie den Wert der `m_nPage` der Membervariable \(Klasse `CMainFrame`\) definieren, Ursachen dieser Technik die Seitenzahl, den Gültigkeitsbereich der Leerlaufverarbeitung dass auf die gleiche Weise angezeigt werden, die Anwendung weitere Indikatoren aktualisiert.  Wenn `m_nPage` ändert, ändert sich die Anzeige während der nächsten Leerlaufschleife.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Benutzeroberfläche aktualisiert, Objekte \(wie Schaltflächen und Menüelemente aktualisiert, wie Programmzustandsänderung\)](../mfc/how-to-update-user-interface-objects.md)  
  
## Siehe auch  
 [Implementieren der Statusleiste mit MFC](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar Class](../mfc/reference/cstatusbar-class.md)