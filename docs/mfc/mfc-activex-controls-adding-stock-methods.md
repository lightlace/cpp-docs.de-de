---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von vordefinierten Methoden"
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
  - "DoClick-Methode"
  - "MFC-ActiveX-Steuerelemente, Methoden"
  - "MFC-ActiveX-Steuerelemente, stock-Methoden"
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von vordefinierten Methoden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine vordefinierte Methode unterscheidet sich von einer benutzerdefinierten Methode, da sie bereits in die [COleControl](../mfc/reference/colecontrol-class.md)\- Klasse implementiert wird.  Beispielsweise enthält vordefinierte `COleControl` eine Memberfunktion, die die Aktualisierungsmethode für das Steuerelement unterstützt.  Der vordefinierte Dispatchzuordnungseintrag für diese Methode lautet **DISP\_STOCKFUNC\_REFRESH**.  
  
 `COleControl` unterstützt zwei vordefinierten Methoden: DoClick und Aktualisierung.  Aktualisierung wird vom Benutzer des Steuerelements aufgerufen, um die Darstellung des Steuerelements auf einmal aktualisieren; DoClick wird aufgerufen, um das Click\-Ereignis des Steuerelements ausgelöst.  
  
|Methode|Dispatchzuordnungseintrag|Kommentar|  
|-------------|-------------------------------|---------------|  
|`DoClick`|**DISP\_STOCKPROP\_DOCLICK\(\)**|Löst ein Click\-Ereignis aus.|  
|**Aktualisieren**|**DISP\_STOCKPROP\_REFRESH\(\)**|Aktualisiert sofort die Darstellung des Steuerelements.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a> Hinzufügen einer vordefinierten Methode mithilfe des Assistenten zum Hinzufügen von Methoden  
 Eine vordefinierte Methode hinzuzufügen ist mit [Assistent zum Hinzufügen von Methoden](../ide/add-method-wizard.md) einfach.  Die folgende Prozedur veranschaulicht das Hinzufügen der Aktualisierungsmethode auf ein Steuerelement, das mit dem MFC\-ActiveX\-Steuerelement\-Assistenten erstellt wird.  
  
#### So der vordefinierten Aktualisierungsmethode mit dem Assistenten zum Hinzufügen von Methoden hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Methode hinzufügen**.  
  
     Dadurch wird der Assistent zum Hinzufügen von Methoden.  
  
5.  Im Feld **Methodenname** klicken Sie auf **Aktualisieren**.  
  
6.  Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a> Assistent zum Hinzufügen von Methodenen\-Änderungen für vordefinierte Methoden  
 Da die vordefinierte Aktualisierungsmethode durch die Basisklasse des Steuerelements unterstützt wird, wird **Assistent zum Hinzufügen von Methoden** nicht die Klassendeklaration des Steuerelements in jeder Hinsicht.  Sie fügt einen Eintrag für die Methode der Dispatchzuordnung des Steuerelements und seiner IDL\-Datei hinzu.  In der folgenden Zeile wird der Dispatchzuordnung des Steuerelements hinzugefügt, in der Implementierungsdatei \(.CPP\):  
  
 [!CODE [NVC_MFC_AxUI#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#16)]  
  
 Dies macht die Aktualisierungsmethode verfügbar für die Benutzer des Steuerelements.  
  
 In der folgenden Zeile wird der IDL\-Datei des Steuerelements hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#17)]  
  
 Diese Zeile weist der Aktualisierungsmethode ein bestimmte ID\-Nummer zu.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)