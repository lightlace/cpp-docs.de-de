---
title: "MFC-ActiveX-Steuerelemente: Verwenden von Bildern in einem ActiveX-Steuerelement"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "LPPICTUREDISP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnDraw-Methode, MFC-ActiveX-Steuerelemente"
  - "MFC ActiveX-Steuerelemente, Bilder"
  - "OnDraw-Methode"
  - "OnResetState-Methode"
  - "CLSID_CPicturePropPage"
ms.assetid: 2e49735c-21b9-4442-bb3d-c82ef258eec9
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Verwenden von Bildern in einem ActiveX-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden der allgemeine Bildtyp und dessen Implementierung in das ActiveX\-Steuerelement beschrieben. Folgende Themen werden behandelt:  
  
-   [Übersicht über benutzerdefinierte Bildeigenschaften](#_core_overview_of_custom_picture_properties)  
  
-   [Implementieren einer benutzerdefinierten Bildeigenschaft in das ActiveX\-Steuerelement](#_core_implementing_a_custom_picture_property_in_your_activex_control)  
  
-   [Zusätze zum Steuerelementprojekt](#_core_additions_to_your_control_project)  
  
##  <a name="_core_overview_of_custom_picture_properties"></a> Übersicht über benutzerdefinierte Bildeigenschaften  
 Der Bildtyp \(Picture\) gehört zu einer Gruppe von Datentypen, die für einige ActiveX\-Steuerelemente verfügbar sind. Dieser Typ behandelt Metadateien, Bitmaps oder Symbole und ermöglicht dem Benutzer die Festlegung eines Bildes, das in einem ActiveX\-Steuerelement angezeigt werden soll. Benutzerdefinierte Bildeigenschaften werden mithilfe eines Bildobjekts und der Get\-\/Set\-Funktionen implementiert, die dem Steuerelementbenutzer den Zugriff auf die Bildeigenschaft ermöglichen. Steuerelementbenutzer greifen über die vordefinierten Bildeeigenschaften auf die benutzerdefinierte Bildeigenschaft zu.  
  
 Neben dem Standardbildtyp sind auch Schriftart\- und Farbtypen verfügbar. Weitere Informationen zur Verwendung des standardmäßigen Schriftarttyps im ActiveX\-Steuerelement finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Verwenden von Schriftarten](../mfc/mfc-activex-controls-using-fonts.md).  
  
 Die ActiveX\-Steuerelementklassen stellen mehrere Komponenten bereit, die Sie zum Implementieren der Bildeigenschaft im Steuerelement verwenden können. Diese Komponenten umfassen:  
  
-   Die [CPictureHolder](../mfc/reference/cpictureholder-class.md)\-Klasse.  
  
     Diese Klasse ermöglicht den einfachen Zugriff auf das Bildobjekt und die Funktionen des Elements, das mittels der benutzerdefinierten Bildeigenschaft angezeigt wird.  
  
-   Unterstützung der Eigenschaften vom Typ **LPPICTUREDISP**, die mit Get\-\/Set\-Funktionen implementiert wurden.  
  
     In der Klassenansicht können Sie schnell eine oder mehrere benutzerdefinierte Eigenschaften hinzufügen, die den Bildtyp unterstützen. Weitere Informationen zum Hinzufügen von ActiveX\-Steuerelementeigenschaften in der Klassenansicht finden Sie unter [MFC\-ActiveX\-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md).  
  
-   Eine Eigenschaftenseite, über die die Bildeigenschaft\(en\) eines Steuerelements geändert werden.  
  
     Diese Eigenschaftenseite ist Bestandteil einer Reihe vordefinierter Eigenschaftenseiten, die für ActiveX\-Steuerelemente verfügbar sind. Weitere Informationen zu Eigenschaftenseiten von ActiveX\-Steuerelementen finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Verwenden von vordefinierten Eigenschaftenseiten](../mfc/mfc-activex-controls-using-stock-property-pages.md).  
  
##  <a name="_core_implementing_a_custom_picture_property_in_your_activex_control"></a> Implementieren einer benutzerdefinierten Bildeigenschaft in das ActiveX\-Steuerelement  
 Nachdem Sie die Schritte in diesem Abschnitt durchgeführt haben, kann das Steuerelement die vom Benutzer ausgewählten Bilder anzeigen. Der Benutzer kann das angezeigte Bild mithilfe einer Eigenschaftenseite ändern, auf der das aktuelle Bild angezeigt wird und die über eine Navigationsschaltfläche verfügt, die dem Benutzer die Auswahl verschiedener Bilder ermöglicht.  
  
 Eine benutzerdefinierte Bildeigenschaft wird in einem ähnlichen Prozess wie andere Eigenschaften implementiert. Der Hauptunterschied liegt darin, dass die benutzerdefinierte Eigenschaft einen Bildtyp unterstützen muss. Da das Element der Bildeigenschaft vom ActiveX\-Steuerelement dargestellt werden muss, müssen eine Reihe von Zusätzen und Änderungen für die Eigenschaft vorgenommen werden, bevor sie vollständig implementiert werden kann.  
  
 Um eine benutzerdefinierte Bildeigenschaft zu implementieren, gehen Sie wie folgt vor:  
  
-   [Fügen Sie dem Steuerelementprojekt Code hinzu](#_core_additions_to_your_control_project).  
  
     Folgendes muss hinzugefügt werden: Eine Eigenschaftenseiten\-ID für die Standardbildeigenschaften, ein Datenmember vom Typ `CPictureHolder` und eine benutzerdefinierte Eigenschaft vom Typ **LPPICTUREDISP** mit einer Get\-\/Set\-Implementierung.  
  
-   [Ändern Sie mehrere Funktionen in der Steuerelementklasse](#_core_modifications_to_your_control_project).  
  
     Diese Änderungen werden für mehrere Funktionen ausgeführt, die für die Darstellung des ActiveX\-Steuerelements verantwortlich sind.  
  
##  <a name="_core_additions_to_your_control_project"></a> Zusätze zum Steuerelementprojekt  
 Um die Eigenschaftenseiten\-ID für die Standardbildeigenschaften hinzuzufügen, fügen Sie in der Implementierungsdatei des Steuerelements \(.CPP\) hinter dem `BEGIN_PROPPAGEIDS`\-Makro die folgende Zeile ein:  
  
 [!CODE [NVC_MFC_AxPic#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#1)]  
  
 Zusätzlich muss der Zählparameter des `BEGIN_PROPPAGEIDS`\-Makros um den Wert 1 erhöht werden. Die folgende Zeile veranschaulicht dies:  
  
 [!CODE [NVC_MFC_AxPic#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#2)]  
  
 Um der Steuerelementklasse den `CPictureHolder`\-Datenmember hinzuzufügen, fügen Sie in der Headerdatei des Steuerelements \(.H\) unter dem protected\-Abschnitt der Deklaration der Steuerelementklasse die folgende Zeile ein:  
  
 [!CODE [NVC_MFC_AxPic#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#3)]  
  
 Es ist nicht notwendig, den Datenmember mit `m_pic` zu benennen, jeder andere Name ist ebenso geeignet.  
  
 Fügen Sie als nächstes eine benutzerdefinierte Eigenschaft hinzu, die einen Bildtyp unterstützt:  
  
#### So fügen Sie eine benutzerdefinierte Bildeigenschaft mit dem Assistenten zum Hinzufügen von Eigenschaften hinzu  
  
1.  Laden Sie das Steuerelementprojekt.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie mit der rechten Maustaste auf den Schnittstellenknoten des Steuerelements \(den zweiten Knoten des Bibliotheksknotens\), um das Kontextmenü zu öffnen.  
  
4.  Wählen Sie im Kontextmenü **Hinzufügen** und dann **Eigenschaft hinzufügen** aus.  
  
5.  Geben Sie im Feld **Eigenschaftsname** den Namen der Eigenschaft ein. In diesem Verfahren wird z. B. `ControlPicture` verwendet.  
  
6.  Wählen Sie im Feld **Eigenschaftstyp** die Option **lPictureDisp\*** als Eigenschaftstyp aus.  
  
7.  Klicken Sie unter **Implementierungstyp** auf **Get\/Set\-Methoden**.  
  
8.  Geben Sie für die Get\- und Set\-Funktion eindeutige Namen ein, oder übernehmen Sie die Standardnamen. \(In diesem Beispiel werden die Standardnamen `GetControlPicture` und `SetControlPicture` verwendet.  
  
9. Klicken Sie auf **Fertig stellen**.  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt den folgenden Code zwischen den Kommentaren der Dispatchzuordnung in der Headerdatei \(.h\) des Steuerelements ein:  
  
 [!CODE [NVC_MFC_AxPic#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#4)]  
  
 Zusätzlich wurde folgender Code in die Dispatchzuordnung der Implementierungsdatei \(.CPP\) des Steuerelements eingefügt:  
  
 [!CODE [NVC_MFC_AxPic#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#5)]  
  
 Der Assistent zum Hinzufügen von Eigenschaften fügt der Implementierungsdatei des Steuerelements auch die folgenden beiden Stubfunktionen hinzu:  
  
 [!CODE [NVC_MFC_AxPic#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#6)]  
  
> [!NOTE]
>  Die von Ihnen verwendeten Steuerelementklassen und Funktionsnamen können von denen im oben genannten Beispiel abweichen.  
  
###  <a name="_core_modifications_to_your_control_project"></a> Änderungen am Steuerelementprojekt  
 Nachdem Sie dem Steuerelementprojekt die notwendigen Zusätze hinzugefügt haben, müssen Sie mehrere Funktionen ändern, die das Rendern des ActiveX\-Steuerelements beeinflussen. Die Funktionen `OnResetState` und `OnDraw` sowie die Get\-\/Set\-Funktionen einer benutzerdefinierten Bildeigenschaft befinden sich in der Implementierungsdatei des Steuerelements. \(Beachten Sie, dass in diesem Beispiel die Steuerelementklasse mit `CSampleCtrl`, der `CPictureHolder`\-Datenmember mit `m_pic` und die benutzerdefinierte Bildeigenschaft mit `ControlPicture` bezeichnet werden.\)  
  
 Fügen Sie in der `OnResetState`\-Funktion des Steuerelements hinter dem Aufruf von `COleControl::OnResetState` die folgende optionale Zeile ein:  
  
 [!CODE [NVC_MFC_AxPic#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#7)]  
  
 Dadurch wird dem Bild des Steuerelements ein leeres Bild zugewiesen.  
  
 Rufen Sie [CPictureHolder::Render](../Topic/CPictureHolder::Render.md) in der `OnDraw`\-Funktion des Steuerelements auf, um das Bild einwandfrei darzustellen. Ändern Sie die Funktion entsprechend dem folgenden Beispiel:  
  
 [!CODE [NVC_MFC_AxPic#8](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#8)]  
  
 Fügen Sie in der Get\-Funktion der benutzerdefinierten Bildeigenschaft des Steuerelements die folgende Zeile hinzu:  
  
 [!CODE [NVC_MFC_AxPic#9](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#9)]  
  
 Fügen Sie in der Set\-Funktion der benutzerdefinierten Bildeigenschaft des Steuerelements die folgenden Zeilen hinzu:  
  
 [!CODE [NVC_MFC_AxPic#10](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#10)]  
  
 Die Bildeigenschaft muss persistent sein, damit beim Entwurf hinzugefügte Informationen zur Laufzeit angezeigt werden. Fügen Sie der `DoPropExchange`\-Funktion der von `COleControl` abgeleiteten Klasse die folgende Zeile hinzu:  
  
 [!CODE [NVC_MFC_AxPic#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxPic#11)]  
  
> [!NOTE]
>  Die von Ihnen verwendeten Klassen und Funktionsnamen können von denen im oben genannten Beispiel abweichen.  
  
 Nachdem Sie die Änderungen vorgenommen haben, erstellen Sie das Projekt neu, um die neue Funktionalität der benutzerdefinierten Bildeigenschaft einzubinden. Testen Sie die neue Eigenschaft dann mit dem Testcontainer. Informationen zum Zugriff auf den Testcontainer finden Sie unter [Testen von Eigenschaften und Ereignissen mit dem Testcontainer](../mfc/testing-properties-and-events-with-test-container.md).  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Verwenden von Schriftarten](../mfc/mfc-activex-controls-using-fonts.md)   
 [MFC\-ActiveX\-Steuerelemente: Eigenschaftenseite](../mfc/mfc-activex-controls-property-pages.md)