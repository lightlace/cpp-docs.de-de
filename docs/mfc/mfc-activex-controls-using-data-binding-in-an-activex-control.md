---
title: "MFC-ActiveX-Steuerelemente: Verwenden der Datenbindung in einem ActiveX-Steuerelement"
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
  - "bindable"
  - "requestedit"
  - "defaultbind"
  - "displaybind"
  - "dispid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gebundene Steuerelemente [C++], MFC-ActiveX"
  - "Steuerelemente [MFC], Datenbindung"
  - "Datenbindung [C++], MFC-ActiveX-Steuerelemente"
  - "Datengebundene Steuerelemente [C++], MFC-ActiveX-Steuerelemente"
  - "MFC-ActiveX-Steuerelemente, Datenbindung"
ms.assetid: 476b590a-bf2a-498a-81b7-dd476bd346f1
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Verwenden der Datenbindung in einem ActiveX-Steuerelement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Einer der leistungsstarkeren Verwendung von ActiveX\-Steuerelementen verwendet die Datenbindung, der eine Eigenschaft des Steuerelements an die Bindung mit einem bestimmten Feld in einer Datenbank ermöglicht.  Wenn ein Benutzer Daten in der gebundenen Eigenschaft ändert, benachrichtigt das Steuerelement die Datenbank und Anforderungen, dass das Datensatzfeld aktualisiert wird.  Die Datenbank dann benachrichtigt das Steuerelement des Erfolgs oder Fehler zu der Anforderung.  
  
 Dieser Artikel enthält die der Aufgabe. Für das Steuerelement  Die Datenbindungsinteraktionen mit der Datenbank zu implementieren ist die Verantwortung des Steuerelementcontainers.  Wie Sie die Datenbankinteraktionen im Container verwalten, ist außerhalb des Umfangs dieser Dokumentation.  Wie Sie bereiten, wird das Steuerelement für Datenbindung im Rest dieses Artikels erläutert.  
  
 ![Konzeptionelles Diagramm eines datengebundenen Steuerelements](../mfc/media/vc374v1.png "vc374V1")  
Konzeptionelles Diagramm eines datengebundenen Steuerelements  
  
 Die `COleControl`\-Klasse stellt zwei Memberfunktionen bereit, die die Datenbindung eines einfachen Prozesses ausführen, um zu implementieren.  Die erste Funktion, [BoundPropertyRequestEdit](../Topic/COleControl::BoundPropertyRequestEdit.md), wird verwendet, um eine Berechtigung erforderlich ist, den Eigenschaftswert zu ändern.  [BoundPropertyChanged](../Topic/COleControl::BoundPropertyChanged.md), die zweite Funktion, wird aufgerufen, nachdem der Eigenschaftswert erfolgreich geändert wurde.  
  
 Dieser Artikel enthält die folgenden Themen:  
  
-   [Erstellen einer bindbaren vordefinierten Eigenschaft](#vchowcreatingbindablestockproperty)  
  
-   [Erstellen einer bindbaren Get\/Set\-Methode](#vchowcreatingbindablegetsetmethod)  
  
##  <a name="vchowcreatingbindablestockproperty"></a> Erstellen einer bindbaren vordefinierten Eigenschaft  
 Es ist möglich, eine datengebundene vordefinierte Eigenschaft zu erstellen, obwohl es wahrscheinlicher ist, dass Sie [bereit get\/Methode, legen Sie fest](#vchowcreatingbindablegetsetmethod) möchten.  
  
> [!NOTE]
>  Vordefinierte Eigenschaften haben die **bindable** und **requestedit**\-Attribute standardmäßig.  
  
#### So einer bindbaren vordefinierten Eigenschaft mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Starten Sie ein Projekt mit [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md).  
  
2.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement mit der rechten Maustaste.  
  
     Dadurch wird das Kontextmenü.  
  
3.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
4.  Wählen Sie einen der Einträge aus der Dropdownliste **Eigenschaft Name**.  Beispielsweise können Sie **Text** auswählen.  
  
     Da **Text** eine vordefinierte Eigenschaft ist, werden die Funktionen **bindable** und **requestedit**\-Attribute bereits überprüft.  
  
5.  Wählen Sie die folgenden Kontrollkästchen von der **IDL\-Attribute** Registerkarte aus: **displaybind** und **defaultbind**, um die Attribute der Eigenschaftendefinition in die IDL\-Datei des Projekts hinzufügen.  Diese Attribute stellen das Steuerelement sichtbar auf das Benutzer und machen die vordefinierte Eigenschaft den Standard bindbare Eigenschaft.  
  
 Nun kann das Steuerelement Daten aus einer Datenquelle angezeigt, kann aber nicht in der Lage, Datenfelder zu aktualisieren.  Wenn Sie das Steuerelement auch in der Lage sein soll, Daten zu aktualisieren, ändern Sie die `OnOcmCommand` \- Funktion [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md), um zu überprüfen, wie folgt:  
  
 [!CODE [NVC_MFC_AxData#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#1)]  
  
 Sie können das Projekt jetzt erstellen, das das Steuerelement registriert.  Wenn Sie das Steuerelement in einem Dialogfeld einfügen, sind **Datenfeld** und die Eigenschaften **Datenquelle** hinzugefügt wurde und Sie können eine Datenquelle und ein Feld jetzt auswählen, die im Steuerelement angezeigt.  
  
##  <a name="vchowcreatingbindablegetsetmethod"></a> Erstellen einer bindbaren Get\/Set\-Methode  
 Neben einem datengebundenen get,\/legen Sie Methode, können Sie auch [bindbare vordefinierte Eigenschaft](#vchowcreatingbindablestockproperty) erstellen fest.  
  
> [!NOTE]
>  Diese Prozedur wird davon ausgegangen, dass ein ActiveX\-Steuerelementprojekt haben, das ein Windows\-Steuerelement als Unterklasse verwendet.  
  
#### Um ein bindbares hinzuzufügen get\/Methode legen Sie mit dem Assistenten zum Hinzufügen von Eigenschaften fest  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Auf der **Steuerelementeinstellungen** Seite wählen Sie eine Fensterklasse aus, damit das Steuerelement als Unterklasse verwendet.  Beispielsweise können Sie ein Bearbeitungssteuerelement unterordnen.  
  
3.  Laden Sie das Projekt des Steuerelements.  
  
4.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement mit der rechten Maustaste.  
  
     Dadurch wird das Kontextmenü.  
  
5.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
6.  Geben Sie den Eigenschaftennamen im Feld **Eigenschaftenname** ein.  Verwenden Sie `MyProp` für dieses Beispiel angezeigt.  
  
7.  Wählen Sie einen Datentyp **Eigenschaftentyp** aus dem Dropdown\-Listenfeld aus.  Verwendung von **short** für dieses Beispiel angezeigt.  
  
8.  Für **Implementierungstyp** auf **Get\/Set\-Methoden**.  
  
9. Wählen Sie die folgenden Kontrollkästchen von der IDL\-Attributregisterkarte aus: **bindable**, **requestedit**, **displaybind** und **defaultbind**, um die Attribute der Eigenschaftendefinition in die IDL\-Datei des Projekts hinzufügen.  Diese Attribute stellen das Steuerelement sichtbar auf das Benutzer und machen die vordefinierte Eigenschaft den Standard bindbare Eigenschaft.  
  
10. Klicken Sie auf **Fertig stellen**.  
  
11. Ändern Sie den Text der `SetMyProp`\-Funktion, damit sie den folgenden Code enthält:  
  
     [!CODE [NVC_MFC_AxData#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#2)]  
  
12. Der Parameter, der den `BoundPropertyChanged` und `BoundPropertyRequestEdit`\-Funktionen übergeben wird, ist das dispid der Eigenschaft, die der Parameter ist, der die id\(\)\- Attribut für die Eigenschaft in der IDL\-Datei übergeben wird.  
  
13. Ändern Sie die [OnOcmCommand](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)\-Funktion enthält, sodass sie den folgenden Code:  
  
     [!CODE [NVC_MFC_AxData#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#1)]  
  
14. Ändern Sie die `OnDraw`\-Funktion, damit sie den folgenden Code enthält:  
  
     [!CODE [NVC_MFC_AxData#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#3)]  
  
15. z öffentlichen Abschnitt der Headerdatei fügen die Headerdatei für die Steuerelementklasse, den folgenden Definitionen \(Konstruktoren\) für Membervariablen hinzu:  
  
     [!CODE [NVC_MFC_AxData#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#4)]  
  
16. Lassen Sie die folgende Zeile die letzte Zeile in `DoPropExchange` arbeiten:  
  
     [!CODE [NVC_MFC_AxData#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#5)]  
  
17. Ändern Sie die `OnResetState`\-Funktion, damit sie den folgenden Code enthält:  
  
     [!CODE [NVC_MFC_AxData#6](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#6)]  
  
18. Ändern Sie die `GetMyProp`\-Funktion, damit sie den folgenden Code enthält:  
  
     [!CODE [NVC_MFC_AxData#7](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxData#7)]  
  
 Sie können das Projekt jetzt erstellen, das das Steuerelement registriert.  Wenn Sie das Steuerelement in einem Dialogfeld einfügen, sind **Datenfeld** und die Eigenschaften **Datenquelle** hinzugefügt wurde und Sie können eine Datenquelle und ein Feld jetzt auswählen, die im Steuerelement angezeigt.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Datengebundene Steuerelemente \(ADO und RDO\)](../data/ado-rdo/data-bound-controls-ado-and-rdo.md)