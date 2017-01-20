---
title: "Meldungsfeldstile"
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
  - "MB_ICONQUESTION"
  - "MB_ICONINFORMATION"
  - "MB_DEFBUTTON2"
  - "MB_YESNO"
  - "MB_OKCANCEL"
  - "MB_TASKMODAL"
  - "MB_ICONEXCLAMATION"
  - "MB_OK"
  - "MB_DEFBUTTON3"
  - "MB_YESNOCANCEL"
  - "MB_APPLMODAL"
  - "MB_RETRYCANCEL"
  - "MB_DEFBUTTON1"
  - "MB_ABORTRETRYIGNORE"
  - "MB_SYSTEMMODAL"
  - "MB_ICONSTOP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MB_ABORTRETRYIGNORE-Konstante"
  - "MB_APPLMODAL-Konstante"
  - "MB_DEFBUTTON1-Konstante"
  - "MB_DEFBUTTON2-Konstante"
  - "MB_DEFBUTTON3-Konstante"
  - "MB_ICONEXCLAMATION-Konstante"
  - "MB_ICONINFORMATION-Konstante"
  - "MB_ICONQUESTION-Konstante"
  - "MB_ICONSTOP-Konstante"
  - "MB_OK-Konstante"
  - "MB_OKCANCEL-Konstante"
  - "MB_RETRYCANCEL-Konstante"
  - "MB_SYSTEMMODAL-Konstante"
  - "MB_TASKMODAL-Konstante"
  - "MB_YESNO-Konstante"
  - "MB_YESNOCANCEL-Konstante"
  - "Meldungsfeldstile"
ms.assetid: d87014c5-4ea4-4950-a27e-7bcdda67be7d
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Meldungsfeldstile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die folgenden Meldungsfeldformate sind verfügbar.  
  
## Message\_Box\-Typen  
  
-   **MB\_ABORTRETRYIGNORE** das Meldungsfeld enthält drei PushButtons: Brechen Sie ab, versuchen Sie erneut und ignorieren Sie.  
  
-   **MB\_OK** das Meldungsfeld enthält einen Pushbutton: OK.  
  
-   **MB\_OKCANCEL** das Meldungsfeld enthält zwei PushButtons: OK und Abbrechen.  
  
-   **MB\_RETRYCANCEL** das Meldungsfeld enthält zwei PushButtons: Wiederholen und Löschen.  
  
-   **MB\_YESNO** das Meldungsfeld enthält zwei PushButtons: Ja und Nein.  
  
-   **MB\_YESNOCANCEL** das Meldungsfeld enthält drei PushButtons: Ja, No und Löschen.  
  
## Meldungsfeld\-Modalität  
  
-   **MB\_APPLMODAL** muss der Benutzer auf das Meldungsfeld reagieren, bevor Arbeit im aktuellen Fenster fortgesetzt.  Die Benutzer können in die Fenster wechseln sowie anderer Anwendungen in diesen Fenstern arbeiten.  Der Standardwert ist **MB\_APPLMODAL**, wenn weder **MB\_SYSTEMMODAL** noch **MB\_TASKMODAL** angegeben ist.  
  
-   **MB\_SYSTEMMODAL** alle Anwendungen werden ignoriert, wenn der Benutzer auf das Meldungsfeld reagiert.  System\-modale Meldungsfelder werden verwendet, um vom Benutzer zu schwer wiegenden, möglicherweise zerstörenden Fehlern zu benachrichtigen, die unmittelbare Aufmerksamkeit erfordern und sparsam eingesetzt werden sollen.  
  
-   **MB\_TASKMODAL MB\_APPLMODAL** ähnlich, aber nicht hilfreich in einer Microsoft Foundations\-Klassen\-Anwendung.  Dieses Flag ist für eine aufrufende Anwendung oder eine Bibliothek reserviert, die nicht verfügbar Fensterhandle hat.  
  
## Meldungsfeld\-Symbole  
  
-   **MB\_ICONEXCLAMATION** ein Ausrufezeichensymbol wird im Meldungsfeld.  
  
-   **MB\_ICONINFORMATION** Symbolbestehen ein "i" in einem Kreis erscheine im Meldungsfeld.  
  
-   Fragezeichensymbol **MB\_ICONQUESTION** A wird im Meldungsfeld.  
  
-   Stoppschildsymbol **MB\_ICONSTOP** A wird im Meldungsfeld.  
  
## Meldungsfeld\-Standardschaltflächen  
  
-   **MB\_DEFBUTTON1** Die erste Schaltfläche ist die Standardeinstellung.  Beachten Sie, dass die erste Schaltfläche immer der Standard ist, es sei denn, **MB\_DEFBUTTON2** oder **MB\_DEFBUTTON3** angegeben ist.  
  
-   **MB\_DEFBUTTON2** Die zweite Schaltfläche ist die Standardeinstellung.  
  
-   **MB\_DEFBUTTON3** Die dritte Schaltfläche ist die Standardeinstellung.  
  
## Siehe auch  
 [Von MFC verwendete Stile](../../mfc/reference/styles-used-by-mfc.md)   
 [AfxMessageBox](../Topic/AfxMessageBox.md)