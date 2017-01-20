---
title: "MFC-ActiveX-Steuerelemente: Weiterf&#252;hrende Eigenschaftenimplementierung"
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
  - "MFC-ActiveX-Steuerelemente, Fehlercodes"
  - "MFC-ActiveX-Steuerelemente, Eigenschaften"
  - "Eigenschaften [MFC], ActiveX-Steuerelemente"
ms.assetid: ec2e6759-5a8e-41d8-a275-99af8ff6f32e
caps.latest.revision: 12
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Weiterf&#252;hrende Eigenschaftenimplementierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Artikel werden die Themen, die zum Implementieren von erweiterten Eigenschaften in einem ActiveX\-Steuerelement verknüpft werden:  
  
-   [Schreibgeschützt und lesegeschützte Eigenschaften](#_core_read2donly_and_write2donly_properties)  
  
-   [Rückgabe von Fehlercodes aus einer Eigenschaft](#_core_returning_error_codes_from_a_property)  
  
##  <a name="_core_read2donly_and_write2donly_properties"></a> Schreibgeschützt und lesegeschützte Eigenschaften  
 Der Assistent zum Hinzufügen von Eigenschaften bietet eine Zeit sparende und einfache Methode, schreib\- oder lesegeschützte Eigenschaften für das Steuerelement implementieren bereit.  
  
#### So ein schreibgeschütztes oder eine lesegeschützte Eigenschaft implementieren  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
     Dadurch wird unter [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  Im Feld **Eigenschaftenname** geben Sie den Namen der Eigenschaft ein.  
  
6.  Für **Implementierungstyp** auf **Get\/Set\-Methoden**.  
  
7.  Im Feld **Eigenschaftentyp** wählen Sie den richtigen Typ für die Eigenschaft aus.  
  
8.  Wenn Sie eine schreibgeschützte Eigenschaft soll, löschen Sie den festgelegten Funktionsnamen.  Wenn Sie eine lesegeschützte Eigenschaft soll, löschen Sie den Abrufensfunktionsnamen.  
  
9. Klicken Sie auf **Fertig stellen**.  
  
 Wenn Sie dies tun, fügt der Assistent zum Hinzufügen von Eigenschaften die Funktion `SetNotSupported` oder `GetNotSupported` im Dispatchzuordnungseintrag anstelle eines normalen Menge ein oder ruft Funktion ab.  
  
 Wenn Sie einer vorhandenen Eigenschaft ändern möchten, um schreibgeschützt oder lesegeschützt sein, können Sie die Dispatchzuordnung manuell bearbeiten und den unnötigen Satz entfernen oder Funktion von der Control\-Klasse abrufen.  
  
 Wenn Sie eine Eigenschaft bedingt schreibgeschützt oder lesegeschützt sein sollen \(beispielsweise, nur, wenn das Steuerelement in einem bestimmten Modus\) funktioniert, können Sie den Satz bereitstellen oder Funktion, z Normal abrufen und rufen die `SetNotSupported` oder Funktion bei `GetNotSupported` auf.  Beispiel:  
  
 [!CODE [NVC_MFC_AxUI#29](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#29)]  
  
 Dieses Codebeispiel ruft `SetNotSupported` auf, wenn der `m_bReadOnlyMode` \- Datenmember **TRUE** ist.  Wenn **FALSE**, anschließend die Eigenschaft auf den neuen Wert festgelegt wird.  
  
##  <a name="_core_returning_error_codes_from_a_property"></a> Rückgabe von Fehlercodes aus einer Eigenschaft  
 Um anzugeben, dass ein Fehler beim Versuch abzurufen, aufgetreten ist, oder, eine Eigenschaft festzulegen, die `COleControl::ThrowError` verwenden Sie die Funktion, `SCODE` \(Statuscode\) als Parameter akzeptiert.  Sie können vordefinierte `SCODE` verwenden oder eine eigene definiert.  Eine Liste vordefinierter `SCODE`s und Anweisungen zum Definieren von benutzerdefiniertem `SCODE`s, finden Sie im Artikel [Fehlerbehandlung im ActiveX\-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX\-Steuerelemente: Weiterführende Themen.  
  
 Hilfsfunktionen sind für die gängigsten vordefinierte `SCODE`s, wie [COleControl::SetNotSupported](../Topic/COleControl::SetNotSupported.md), [COleControl::GetNotSupported](../Topic/COleControl::GetNotSupported.md) und [COleControl::SetNotPermitted](../Topic/COleControl::SetNotPermitted.md).  
  
> [!NOTE]
>  `ThrowError` gilt, nur als Mittel zur Rückgabe eines Fehlers aus einer Eigenschaft verwendet werden abrufen oder festlegen Funktion oder eine Automatisierungsmethode.  Dies sind die einzigen vorkommen, dass der entsprechende Ausnahmehandler auf dem Stapel vorhanden ist.  
  
 Weitere Informationen über Berichterstellungsausnahmen in anderen Bereichen des Codes, finden Sie unter [COleControl::FireError](../Topic/COleControl::FireError.md) und im Abschnitt [Fehlerbehandlung im ActiveX\-Steuerelement](../mfc/mfc-activex-controls-advanced-topics.md) im Artikel ActiveX\-Steuerelemente: Weiterführende Themen.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)