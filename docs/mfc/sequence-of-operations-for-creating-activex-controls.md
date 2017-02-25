---
title: "Operationssequenz zur Erstellung von ActiveX-Steuerelementen | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [C++], Erstellen"
  - "MFC ActiveX-Steuerelemente [C++], Erstellen"
  - "OLE-Steuerelemente [C++], MFC"
  - "Reihenfolge [C++]"
  - "Reihenfolge [C++], Zum Erstellen von ActiveX-Steuerelementen"
ms.assetid: 7d868c53-a0af-4ef6-a89c-e1c03c583a53
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Operationssequenz zur Erstellung von ActiveX-Steuerelementen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der folgenden Tabelle wird die Rolle und die Rolle des Frameworks an, wenn dieser ActiveX\-Steuerelemente erstellt \(früher bekannt als OLE\-Steuerelemente\).  
  
### Erstellen von ActiveX\-Steuerelementen  
  
|Aufgabe|Hierzu|Das Framework führt|  
|-------------|------------|-------------------------|  
|Erstellen Sie ein ActiveX\-Steuerelement\-Framework.|Führen Sie den MFC\-ActiveX\-Steuerelement\-Assistenten aus, um das Steuerelement zu erstellen.  Geben Sie die Optionen, die Sie in den Optionsseiten soll.  Optionen enthalten den Typ und den Namen des Steuerelements im Projekt, in der Lizenzierung, dem Erstellen von Unterklassen und etwa in einer Feldmethode.|Der MFC\-ActiveX\-Steuerelement\-Assistent erstellt die Dateien für ein ActiveX\-Steuerelement mit grundlegenden Funktionalität, z Quelldateien für die Anwendung, Steuerelement und Eigenschaftenseite oder Seiten; ; eine Ressourcendatei eine Projektdatei; und andere, so angepasst zu der Spezifikation.|  
|Siehe, was das Steuerelement und der ActiveX\-Steuerelement\-Assistent bieten, ohne eine Zeile eigenen Code hinzuzufügen.|Erstellen Sie das ActiveX\-Steuerelement und testen Sie es mit Internet Explorer oder [TSTCON\-Beispiel](../top/visual-cpp-samples.md).|Das ausgeführte Steuerelement hat die Fähigkeit zu ändernde und verschieben.  Es enthält außerdem eine **Infofeld**\-Methode \(wenn ausgewählt werden\), die aufgerufen werden kann.|  
|Implementieren Sie die Methoden und Eigenschaften des Steuerelements.|Implementieren Sie Ihre steuerelementspezifischen Methoden und Eigenschaften, indem Sie Memberfunktionen hinzu, um eine verfügbar gemachte Schnittstelle auf die Daten des Steuerelements bereitzustellen.  Fügen Sie Membervariablen hinzu, um Datenstrukturen verwendet und Ereignishandler nutzen, um Ereignisse auszulösen, wenn Sie feststellen.|Das Framework hat bereits eine Zuordnung definiert, um die Ereignisse des Steuerelements, Eigenschaften zu unterstützen und Methoden und Ihnen überlassen, konzentrieren können auf, wie die Eigenschaften und Methoden implementiert werden.  Die Standardeigenschaftsseite ist sichtbar und ein Standard zu Feldmethode angegeben wird.|  
|Erstellen Sie die Eigenschaftenseite oder die Seiten des Steuerelements.|Verwenden Sie die Visual C\+\+\-Ressourcen\-Editoren, um die Eigenschaftenseitenschnittstelle des Steuerelements zu bearbeiten:<br /><br /> -   Erstellen Sie zusätzliche Eigenschaftenseiten.<br />-   Erstellen und Bearbeiten von Bitmaps, Symbole und Cursor.<br /><br /> Sie können die Eigenschaftenseite im Dialog\-Editor auch testen.|Die Standardressourcendatei, die vom MFC\-Anwendungs\-Assistenten erstellt wird, enthält viele Ressourcen, die Sie benötigen.  Visual C\+\+ können Sie vorhandene Ressourcen bearbeiten und neue Ressourcen problemlos und visuell hinzufügen.|  
|Testen Sie die Ereignisse, die Methoden und Eigenschaften des Steuerelements.|Erstellen des Steuerelements und dem Testcontainer neu, um zu testen, dass die Handler ordnungsgemäß funktionieren.|Sie können die Methoden des Steuerelements aufrufen und die zugehörigen Eigenschaften über die Eigenschaftenseitenschnittstelle Testcontainer oder durch Bearbeiten.  Außerdem dem Testcontainer an Laufwettbewerben vom Steuerelement ausgelöst und von Benachrichtigungen empfangen vom Container des Steuerelements.|  
  
## Siehe auch  
 [Erstellen im Framework](../mfc/building-on-the-framework.md)   
 [Reihenfolge der Operationen zur Erstellung von MFC\-Anwendungen](../mfc/sequence-of-operations-for-building-mfc-applications.md)   
 [Reihenfolge der Operationen zur Erstellung von OLE\-Anwendungen](../mfc/sequence-of-operations-for-creating-ole-applications.md)   
 [Reihenfolge der Operationen zur Erstellung Datenbankanwendungen](../mfc/sequence-of-operations-for-creating-database-applications.md)