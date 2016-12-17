---
title: "Validieren von Dialogfelddaten"
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
  - "Datenvalidierung [C++], Dialogfelder"
  - "Datenvalidierung [C++], Meldungsfelder"
  - "DDV (Dialogfelddatenvalidierung) [C++]"
  - "Dialogfelder [C++], Validieren von Daten"
  - "Daten validieren [C++], Dialogfeld-Dateneingabe"
  - "Daten validieren [C++], Meldungsfelder"
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Validieren von Dialogfelddaten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können die Validierung zusätzlich zum Datenaustausch angeben, indem Sie DDV\-Funktionen, wie das Beispiel in [Dialogdatenaustausch](../mfc/dialog-data-exchange.md) gezeigt.  Der Aufruf `DDV_MaxChars` im Beispiel überprüft, ob die Zeichenfolge, die in das Textfeld\-Steuerelement eingegeben wird, nicht mehr als 20 Zeichen umfasst.  Die DDV\-Funktion weist in der Regel dem ein Meldungsfeld, wenn die Validierung den Fokus auf das problemauslösende Steuerelement verlässt und Fortfahren, damit der Benutzer Daten erneut eingeben kann.  Eine DDV\-Funktion für ein gegebenes Steuerelement muss aufgerufen werden, nachdem die DDX\-Funktion für gleich steuern.  
  
 Sie können eigene benutzerdefinierte DDX und DDV\-Routinen auch definieren.  Ausführliche Informationen über diese und andere Aspekte von DDX und von DDV, finden Sie unter [MFC\-technischer Hinweis 26](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) werden alle DDX\- und DDV\-Aufrufe in der Datenumsetzung für Sie.  
  
## Siehe auch  
 [Dialogdatenaustausch und \-validierung](../mfc/dialog-data-exchange-and-validation.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Dialogdatenaustausch](../mfc/dialog-data-exchange.md)