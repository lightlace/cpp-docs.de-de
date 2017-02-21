---
title: "MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von benutzerdefinierten Eigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelemente, Eigenschaften"
  - "Eigenschaften [MFC], Benutzerdefiniert"
ms.assetid: 85af5167-74c7-427b-b8f3-e0d7b73942e5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC-ActiveX-Steuerelemente: Hinzuf&#252;gen von benutzerdefinierten Eigenschaften
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Benutzerdefinierte Eigenschaften unterscheiden sich von vordefinierten Eigenschaften in diesem benutzerdefinierte Eigenschaften werden nicht bereits implementiert durch die `COleControl`\-Klasse.  Eine benutzerdefinierte Eigenschaft wird verwendet, um einen bestimmten Zustand oder eine Darstellung eines ActiveX\-Steuerelements einen Programmierer verfügbar zu machen, der das Steuerelement verwendet.  
  
 Dieser Artikel beschreibt, wie einer benutzerdefinierten Eigenschaft zum ActiveX\-Steuerelement mithilfe des Assistenten zum Hinzufügen von Eigenschaften hinzufügt und beschreibt die resultierenden Codeänderungen.  Folgende Themen werden behandelt:  
  
-   [Mit dem Assistenten zum Hinzufügen von Eigenschaften, um eine benutzerdefinierte Eigenschaft hinzu](#_core_using_classwizard_to_add_a_custom_property)  
  
-   [Assistent zum Hinzufügen von Eigenschaftenen\-Änderungen für benutzerdefinierte Eigenschaften](#_core_classwizard_changes_for_custom_properties)  
  
 Benutzerdefinierte Eigenschaften sind in vier Varianten der Implementierung: Membervariablen, Membervariable mit Benachrichtigungen, Get\/und Set\-Methoden parametrisiert.  
  
-   Membervariablen\-Implementierung  
  
     Diese Implementierung wird der Zustand der Eigenschaft als Membervariable in der Steuerelementklasse dar.  Verwenden Sie die Membervariablenimplementierung, wenn es nicht wichtig ist, zu wissen, wann der Eigenschaftswert ändert.  Von den drei Typen erstellt dieser Implementierung die wenigsten Menge Stützcodes für die Eigenschaft.  Das Dispatchzuordnungseintragsmakro für Membervariablenimplementierung ist [DISP\_PROPERTY](../Topic/DISP_PROPERTY.md).  
  
-   Membervariable mit Benachrichtigungs\-Implementierung  
  
     Diese Implementierung wird eine Membervariable und einer Benachrichtigungsfunktion, die vom Assistenten zum Hinzufügen von Eigenschaften erstellt werden.  Die Benachrichtigungsfunktion wird automatisch vom Framework aufgerufen, nachdem der Eigenschaftswert ändert.  Verwenden Sie die Membervariable mit Benachrichtigungsimplementierung, wenn Sie benachrichtigt werden, nachdem ein Eigenschaftswert geändert wurde.  Diese Implementierung erfordert mehr Zeit, da sie einen Funktionsaufruf erfordert.  Das Dispatchzuordnungseintragsmakro für diese Implementierung ist [DISP\_PROPERTY\_NOTIFY](../Topic/DISP_PROPERTY_NOTIFY.md).  
  
-   Get\/Set\-Methoden\-Implementierung  
  
     Diese Implementierung besteht aus einem Memberfunktionen in der Steuerelementklasse.  Die Get\/Set\-Methodenimplementierung wird automatisch die Abrufensmemberfunktion auf, wenn der Benutzer anfordert des Steuerelements der aktuelle Wert der Eigenschaft und der festgelegte Member wenn die Benutzeranforderungen des Steuerelements arbeiten, die die Eigenschaft geändert wird.  Verwenden Sie diese Implementierung, wenn Sie den Wert einer Eigenschaft während der Laufzeit berechnen, einen Wert überprüfen müssen, der vom Benutzer des Steuerelements übergeben wird, bevor die tatsächliche Eigenschaft ändern, oder einen gelesenen oder lesegeschützter Eigenschaft Typ implementieren.  Das Dispatchzuordnungseintragsmakro für diese Implementierung ist [DISP\_PROPERTY\_EX](../Topic/DISP_PROPERTY_EX.md).  Der folgende Abschnitt, [Mit dem Assistenten zum Hinzufügen von Eigenschaften, um eine benutzerdefinierte Eigenschaft hinzu](#_core_using_classwizard_to_add_a_custom_property), wird die benutzerdefinierte Eigenschaft CircleOffset, diese Implementierung zu veranschaulichen.  
  
-   Parametrisierte Implementierung  
  
     Parametrisierte Implementierung wird im Assistenten zum Hinzufügen von Eigenschaften unterstützt.  Eine parametrisierte Eigenschaft \(gelegentlich aufgerufen ein Eigenschaftenarray\) kann verwendet werden, um einen Satz von Werten auf eine einzelne Eigenschaft des Steuerelements zuzugreifen.  Das Dispatchzuordnungseintragsmakro für diese Implementierung ist `DISP_PROPERTY_PARAM`.  Weitere Informationen zum Implementieren dieses Typs, finden Sie im Artikel [Implementieren einer parametrisierten Eigenschaft](../mfc/mfc-activex-controls-advanced-topics.md) in ActiveX\-Steuerelemente: Weiterführende Themen.  
  
##  <a name="_core_using_classwizard_to_add_a_custom_property"></a> Mit dem Assistenten zum Hinzufügen von Eigenschaften, um eine benutzerdefinierte Eigenschaft hinzu  
 Die folgende Prozedur veranschaulicht das Hinzufügen einer benutzerdefinierten Eigenschaft, CircleOffset, das die Get\/Set\-Methodenimplementierung verwendet.  Die benutzerdefinierte CircleOffset Eigenschaft können Benutzer des Steuerelements, um den Kreis vom Mittelpunkt des umgebenden Rechtecks des Steuerelements.  Die Verfahren zum Hinzufügen von benutzerdefinierten Eigenschaften mit einer Implementierung als Get\/Set\-Methoden ist sehr ähnlich.  
  
 Derselbe Prozedur kann auch verwendet werden, um andere benutzerdefinierte Eigenschaften hinzuzufügen, werden.  Ersetzen Sie den benutzerdefinierten Eigenschaftennamen für den Eigenschaftennamen und die Parameter CircleOffset.  
  
#### So fügen die benutzerdefinierte Eigenschaft CircleOffset mit dem Assistenten zum Hinzufügen von Eigenschaften hinzufügen  
  
1.  Laden Sie das Projekt des Steuerelements.  
  
2.  Erweitern Sie in der Klassenansicht den Bibliotheksknoten des Steuerelements.  
  
3.  Klicken Sie auf den Schnittstellenknoten für das Steuerelement \(der zweite Knoten des Bibliotheksknotens\) mit der rechten Maustaste um das Kontextmenü zu öffnen.  
  
4.  Klicken Sie im Kontextmenü auf **Hinzufügen** und dann auf **Eigenschaft hinzufügen**.  
  
     Dadurch wird unter [Assistent zum Hinzufügen von Eigenschaften](../ide/names-add-property-wizard.md).  
  
5.  Im Feld **Eigenschaftenname** geben Sie `CircleOffset` ein.  
  
6.  Für **Implementierungstyp** auf **Get\/Set\-Methoden**.  
  
7.  Im Feld **Eigenschaftentyp** die Option **short** aus.  
  
8.  Eindeutige Namen des Typs für das rufen Funktionen ab und legen fest oder übernehmen die Standardnamen.  
  
9. Klicken Sie auf **Fertig stellen**.  
  
##  <a name="_core_classwizard_changes_for_custom_properties"></a> Assistent zum Hinzufügen von Eigenschaftenen\-Änderungen für benutzerdefinierte Eigenschaften  
 Wenn Sie die benutzerdefinierte Eigenschaft CircleOffset hinzufügen, wird der Assistent zum Hinzufügen von Eigenschaften Änderungen der Header vor \(.H\) und Dateien die Implementierungsdatei \(.CPP\) der Steuerelementklasse.  
  
 Die folgenden Zeilen werden hinzugefügt. H\-Datei, von zwei Funktionen zu deklarieren dem Namen `GetCircleOffset` und `SetCircleOffset` auf:  
  
 [!CODE [NVC_MFC_AxUI#25](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#25)]  
  
 In der folgenden Zeile wird der IDL\-Datei des Steuerelements hinzugefügt:  
  
 [!CODE [NVC_MFC_AxUI#26](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#26)]  
  
 Diese Zeile weist der CircleOffset\-Eigenschaft ein die bestimmte ID\-Nummer zu, aufgezeichnet von der Position der Methode in Methoden und in der Liste des Assistenten zum Hinzufügen von Eigenschaften.  
  
 Außerdem wird die folgende Zeile in die Dispatchzuordnung \(in die CPP\-Datei der Steuerelementklasse\) hinzugefügt um der CircleOffset\-Eigenschaft an Handlerfunktionen des Steuerelements zwei zuzuweisen:  
  
 [!CODE [NVC_MFC_AxUI#27](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#27)]  
  
 Schließlich werden Implementierungen die `GetCircleOffset` und `SetCircleOffset` Features zum Ende der CPP\-Datei des Steuerelements hinzugefügt.  In den meisten Fällen ändern Sie die Abrufensfunktion, um den Wert der Eigenschaft zurückgegeben.  Die festgelegte Funktion enthält normalerweise Code, der ausgeführt werden soll, entweder vor oder nach der Eigenschaft ändert.  
  
 [!CODE [NVC_MFC_AxUI#28](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#28)]  
  
 Beachten Sie, dass der Assistent zum Hinzufügen von Eigenschaften automatisch einen Aufruf, [SetModifiedFlag](../Topic/COleControl::SetModifiedFlag.md), Text der festgelegten Funktion hinzufügt.  Diese Funktion aufrufen, markiert das Steuerelement, z geändert.  Wenn ein Steuerelement geändert wurde, wird sein neuen Zustand gespeichert, wenn der Container gespeichert wird.  Diese Funktion sollte aufgerufen werden, wenn eine Eigenschaft gespeichert worden als Teil des dauerhaften Zustands des Steuerelements, Änderungswert.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)   
 [MFC\-ActiveX\-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md)   
 [MFC\-ActiveX\-Steuerelemente: Methoden](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)