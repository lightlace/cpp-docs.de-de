---
title: "MFC-ActiveX-Steuerelemente: Methoden | Microsoft Docs"
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
  - "MFC-ActiveX-Steuerelemente, Methoden"
ms.assetid: e20271de-6ffa-4ba0-848b-bafe6c9e510c
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Methoden
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein ActiveX\-Steuerelement löst Ereignisse aus, um sich zwischen und seinem Steuerelementcontainer zu kommunizieren.  Ein Container kann ein Steuerelement mithilfe der Methoden und Eigenschaften auch kommunizieren.  Methoden sind auch aufgerufene Funktionen.  
  
 Methoden und Eigenschaften stellen eine exportierte Schnittstelle für andere Anwendungen, z Automatisierungsclients und ActiveX\-Steuerelementcontainer bereit.  Weitere Informationen über ActiveX\-Steuerelementeigenschaften, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Eigenschaften](../mfc/mfc-activex-controls-properties.md).  
  
 Methoden sind ähnlich gebräuchliches und beabsichtigen zu Memberfunktionen von eine C\+\+\-Klasse.  Es gibt zwei Typen von Methoden, die das Steuerelement implementieren kann: Bestand und Custom.  Ähnlich den vordefinierten Ereignisse sind vordefinierte, Methoden diese Methoden, für die [COleControl](../mfc/reference/colecontrol-class.md) eine Implementierung bereitstellt.  Weitere Informationen über vordefinierte Methoden, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md).  Die benutzerdefinierten Methoden definiert, dem Entwickler, können weitere Anpassungen des Steuerelements.  Weitere Informationen finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden](../mfc/mfc-activex-controls-adding-custom-methods.md).  
  
 Die Microsoft Foundation Class\-Bibliothek " \(MFC\-Bibliothek\) implementiert einen Mechanismus, der das Steuerelement an Stützvordefinierten und benutzerdefinierten Methoden zulässig.  Der erste Teil ist die Klasse `COleControl`.  Ist von `CWnd`, `COleControl`\-Memberfunktionsstützvorratmethoden, die allen ActiveX\-Steuerelemente häufig sind.  Der zweite Teil dieses Mechanismus ist die Dispatchzuordnung.  Eine Dispatchzuordnung ist einer Meldungszuordnung ähnlich; jedoch, anstatt einer Funktion einer Windows\-Meldung ID zugeordnet zu, wird eine Dispatchzuordnung virtuellen Memberfunktionen zu IDispatch\-IDS.  
  
 Damit Steuerelemente ordnungsgemäß verschiedene Möglichkeiten, die Klasse muss eine Dispatchzuordnung deklarieren unterstützt.  Dies wird durch die folgende Codezeile in der Steuerelementklassenkopfzeile erreicht \(.H\) Datei:  
  
 [!CODE [NVC_MFC_AxUI#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#13)]  
  
 Der primäre Zweck der Dispatchzuordnung ist, die Beziehung zwischen den Methodennamen, die von einem externen Aufrufer \(verwendet werden wie dem Container\) und Memberfunktionen der Klasse des Steuerelements erstellen, die die Methoden implementieren.  Nachdem die Dispatchzuordnung deklariert wurde, muss sie in der Implementierung des Steuerelements definiert werden \(.CPP\).  Die folgenden Codezeilen werden die Dispatchzuordnung:  
  
 [!CODE [NVC_MFC_AxUI#14](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#14)]  
[!CODE [NVC_MFC_AxUI#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#15)]  
  
 Wenn Sie [MFC\-ActiveX\-Steuerelement\-Assistent](../mfc/reference/mfc-activex-control-wizard.md) verwenden, um das Projekt zu erstellen, wurden diese Zeilen automatisch hinzugefügt.  Wenn der MFC\-ActiveX\-Steuerelement\-Assistent nicht verwendet wurde, müssen Sie diese manuell Zeilen hinzufügen.  
  
 Die folgenden Elemente werden Methoden ausführlich erörtert:  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen vordefinierter Methoden](../mfc/mfc-activex-controls-adding-stock-methods.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Hinzufügen von benutzerdefinierten Methoden](../mfc/mfc-activex-controls-adding-custom-methods.md)  
  
-   [MFC\-ActiveX\-Steuerelemente: Rückgabe von Fehlercodes aus einer Methode](../mfc/mfc-activex-controls-returning-error-codes-from-a-method.md)  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)