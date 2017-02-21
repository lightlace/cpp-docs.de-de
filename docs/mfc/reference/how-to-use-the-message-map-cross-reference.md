---
title: "Gewusst wie: Verwenden des Meldungszuordnungs-Querverweises | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fenster [C++], Meldungszuordnungen"
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Gewusst wie: Verwenden des Meldungszuordnungs-Querverweises
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In den Einträgen, die memberFxn \<\>beschriftet sind, schreiben Sie Ihre eigene Memberfunktion für eine abgeleitete Klasse [CWnd](../../mfc/reference/cwnd-class.md).  Geben Sie der Funktion einen beliebigen Namen, den Sie möchten.  Andere Funktionen, wie `OnActivate`, können Memberfunktionen der Klasse `CWnd`.  Wenn sie aufgerufen werden, wird die Meldung an die Windows\-Funktion `DefWindowProc` weiter.  Um Windows\-Benachrichtigungsmeldungen verarbeiten, überschreiben Sie die entsprechende Funktion `CWnd` in der abgeleiteten Klasse.  Ihre Funktion sollte die überschriebene Funktion in der Basisklasse aufrufen, um die Basisklasse und Windows auf die Meldung reagiert wird.  
  
 In allen Fällen sollten Sie den `CWnd`\- Header Funktionsprototyp in der abgeleiteten Klasse ein, und codieren Sie den Eintrag in der Meldungszuordnung wie dargestellt.  
  
 Die folgenden Begriffe werden verwendet:  
  
|Begriff|Definition|  
|-------------|----------------|  
|id|Jede benutzerdefinierte Menüelement ID \(**WM\_COMMAND** Meldungen\) oder \(Benachrichtigungsmeldungen Steuerelement\-ID des untergeordneten Fensters\).|  
|"Meldung" und "wNotifyCode"|Windows\-Meldungs\-IDs, wie in WINDOWS.H. definiert.|  
|nMessageVariable|Name einer Variablen, die den Rückgabewert der Windows\-Funktion **RegisterWindowMessage** enthält.|  
  
## Siehe auch  
 [Meldungszuordnungen](../../mfc/reference/message-maps-mfc.md)