---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von benutzerdefinierten Methoden"
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
  - "MFC-ActiveX-Steuerelemente, Methoden"
  - "PtInCircle (benutzerdefinierte Methode)"
ms.assetid: 8f8dc344-44a0-4021-8db5-4cdd3d700e18
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von benutzerdefinierten Methoden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benutzerdefinierte Methoden unterscheiden sich von vordefinierten Methoden, da sie nicht bereits von `COleControl` implementiert werden.  Sie müssen die Implementierung für jede benutzerdefinierte Möglichkeit bieten, die Sie dem Steuerelement hinzufügen.  
  
 Ein ActiveX\-Steuerelement\-Benutzer kann eine benutzerdefinierte Methode jederzeit aufrufen, um steuerelementspezifische Aktionen auszuführen.  Der Dispatchzuordnungseintrag für benutzerdefinierte Methoden hat die Form `DISP_FUNCTION`.  
  
##  <a name="_core_adding_a_custom_method_with_classwizard"></a> Hinzufügen einer benutzerdefinierten Methode mit dem Assistenten zum Hinzufügen von Methoden  
 Die folgende Prozedur veranschaulicht das Hinzufügen der benutzerdefinierten Methode PtInCircle einem Codeskelett des ActiveX\-Steuerelements.  Innerhalb PtInCircle bestimmt, ob die Koordinaten, die dem Steuerelement übergeben werden oder außerhalb des Kreises sind.  Derselbe Prozedur kann auch verwendet werden, um andere benutzerdefinierte Methoden hinzuzufügen.  Ersetzen Sie den benutzerdefinierten Methodennamen und die Parameter für den PtInCircle\-Methodennamen und Parameter zu variieren.  
  
> [!NOTE]
>  Dieses Beispiel verwendet die `InCircle`\-Funktion von den Artikel Ereignissen.  Weitere Informationen über diese Funktion, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Hinzufügen von benutzerdefinierten Ereignissen in einem ActiveX\-Steuerelement](../mfc/mfc-activex-controls-adding-custom-events.md).  
  
#### So fügen die benutzerdefinierte Methode PtInCircle mit dem Assistenten zum Hinzufügen von Methoden hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Methode hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Methoden.  
  
5.  Im Feld **Methodenname** geben Sie `PtInCircle` ein.  
  
6.  Im Feld **Interner Name** geben Sie den Namen der internen Funktion der Art oder verwenden Sie den Standardwert \(in diesem Fall, `PtInCircle`\).  
  
7.  Im Feld **Rückgabetyp** klicken Sie auf **VARIANT\_BOOL** für den Rückgabetyp der Methode.  
  
8.  Verwenden von **Parametertyp** und **Parametername**\-Steuerelementen fügen Sie einen Parameter hinzu, der `xCoord` \( **OLE\_XPOS\_PIXELS**\-Typ\) bezeichnet wird.  
  
9. Verwenden von **Parametertyp** und **Parametername**\-Steuerelementen fügen Sie einen Parameter hinzu, der `yCoord` \( **OLE\_YPOS\_PIXELS**\-Typ\) bezeichnet wird.  
  
10. Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_custom_methods"></a> Assistent zum Hinzufügen von Methodenen\-Änderungen für benutzerdefinierte Methoden  
 Wenn Sie eine benutzerdefinierte Methode hinzufügen, wird der Assistent zum Hinzufügen von Methoden einige Änderungen an der Steuerelementklassenkopfzeile vor \(.H\) und die Implementierungsdatei \(.CPP\).  In der folgenden Zeile wird der Dispatchzuordnungsdeklaration in der Steuerelementklassenkopfzeile hinzugefügt \(.H\) Datei:  
  
 [!CODE [NVC_MFC_AxUI#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#18)]  
  
 Dieser Code deklariert eine Dispatchmethode Handler mit dem Namen `PtInCircle`.  Diese Funktion kann im Steuerelementbenutzer aufgerufen werden, der den externen Namen PtInCircle verwendet.  
  
 In der folgenden Zeile wird der IDL\-Datei des Steuerelements hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#19](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#19)]  
  
 Diese Zeile weist der PtInCircle\-Methode ein bestimmte ID\-Nummer, die Position der Methode in den Assistenten zum Hinzufügen von Methodenen\-Methoden und Liste zu.  Da der Assistent zum Hinzufügen von Methoden verwendet wurde, um die benutzerdefinierte Methode hinzuzufügen, wurde der Eintrag für ihn automatisch der IDL\-Datei des Projekts hinzugefügt.  
  
 Außerdem wird die folgende Zeile, in der Implementierungsdatei \(.CPP\) der Steuerelementklasse, zur Dispatchzuordnung des Steuerelements hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#20](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#20)]  
  
 Das Makro `DISP_FUNCTION` ordnet der Methode PtInCircle an die Handlerfunktion des Steuerelements, `PtInCircle`, deklariert den Rückgabetyp, um **VARIANT\_BOOL** sind und deklariert zwei Parameter des Typs an `PtInCircle` übergeben werden **VTS\_XPOS\_PIXELS**  und **VTS\_YPOSPIXELS**.  
  
 Abschließend fügt der Assistent zum Hinzufügen von Methoden die Stubfunktion `CSampleCtrl::PtInCircle` der Unterkante der Implementierung des Steuerelements \(.CPP\) hinzu.  Damit `PtInCircle` funktioniert, wie bereits erwähnt, muss er geändert werden, wie folgt:  
  
 [!CODE [NVC_MFC_AxUI#21](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#21)]  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [Symbole in der Klassenansicht und im Objektbrowser](../Topic/Class%20View%20and%20Object%20Browser%20Icons.md)