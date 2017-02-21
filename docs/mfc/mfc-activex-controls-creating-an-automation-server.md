---
title: "MFC-ActiveX-Steuerelemente: Erstellen eines Automatisierungsservers | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [C++], Automatisierungsserver"
  - "Automatisierungsserver [C++], MFC-ActiveX-Steuerelemente"
  - "MFC ActiveX-Steuerelemente [C++], Automatisierungsserver"
ms.assetid: e0c24ed2-d61c-49ad-a4fa-4e1098d1d39b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# MFC-ActiveX-Steuerelemente: Erstellen eines Automatisierungsservers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können ein MFC\-ActiveX\-Steuerelement als Automatisierungsserver entwickeln, mit dem Ziel programmgesteuert einbetten dass Steuerelement in einer anderen Anwendung und Aufrufen von Methoden im Steuerelement der Anwendung.  Ein solches Steuerelement würde weiterhin verfügbar sein, in einen ActiveX\-Steuerelementcontainer gehostet werden.  
  
### Um ein Steuerelement als Automatisierungsserver erstellen  
  
1.  [Erstellen](../mfc/reference/mfc-activex-control-wizard.md) das Steuerelement.  
  
2.  [Fügen Sie Methoden hinzu](../mfc/mfc-activex-controls-methods.md).  
  
3.  Überschreibung [IsInvokeAllowed](../Topic/COleControl::IsInvokeAllowed.md).  Weitere Informationen finden Sie im Artikel Q146120 der Knowledge Base \(nur auf Englisch verfügbar\).  
  
4.  Erstellen Sie das Steuerelement.  
  
### Um auf die Methoden in einen Automatisierungsserver programmgesteuert zugreifen  
  
1.  Erstellen Sie eine Anwendung zum Beispiel [MFC\-exe](../mfc/reference/mfc-application-wizard.md).  
  
2.  am Anfang der `InitInstance`\-Funktion fügen Sie die folgende Zeile hinzu:  
  
     [!CODE [NVC_MFC_AxCont#17](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#17)]  
  
3.  Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Klasse aus typelib hinzufügen** aus der Typbibliothek importiert.  
  
     Dies fügt Dateien mit den Dateinamenerweiterungen H\-Dateien und .cpp dem Projekt hinzu.  
  
4.  In der Headerdatei der Klasse, in der Sie eine oder mehrere Methoden im ActiveX\-Steuerelement aufrufen, die folgende Zeile hinzu: `#include filename.h`, wo Dateiname den Namen der Headerdatei ist, die erstellt wurde, als Sie die Typbibliothek importiert haben.  
  
5.  In der Funktion, in der ein Aufruf einer Methode im ActiveX\-Steuerelement ausgeführt wird, fügen Sie Code, der ein Objekt der Wrapperklasse des Steuerelements erstellt hinzu und erstellen Sie das ActiveX\-Objekt.  Beispielsweise instanziiert der folgende MFC\-Code ein `CCirc`\-Steuerelement, ruft die Beschriftungseigenschaft ab und zeigt das Ergebnis, wenn auf die Schaltfläche OK in einem Dialogfeld geklickt wird:  
  
     [!CODE [NVC_MFC_AxCont#18](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxCont#18)]  
  
 Wenn Sie Methoden dem ActiveX\-Steuerelement hinzufügen, nachdem Sie es in einer Anwendung verwenden, können Sie mit der aktuellen Version des Steuerelements in der Anwendung starten, indem Sie die Dateien gelöscht haben, die erstellt wurden, als Sie die Typbibliothek importiert haben.  Importieren Sie dann erneut die Typbibliothek.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)