---
title: "&#220;berschreibbare Memberfunktionen"
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
  - "CDialog-Klasse, Member"
  - "Dialogklassen, Üblicherweise überschriebene Memberfunktionen"
  - "MFC-Dialogfelder, Überschreiben von Memberfunktionen"
  - "OnCancel-Funktion"
  - "OnInitDialog-Funktion"
  - "OnOK-Funktion"
  - "Überschreiben, Dialogklassenmember"
ms.assetid: 78eb566c-e361-4c86-8db5-c7e2791b249a
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# &#220;berschreibbare Memberfunktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die folgende Tabelle zeigt wahrscheinlichsten die Memberfunktionen auf, um im `CDialog` zu überschreiben abgeleiteten Klasse.  
  
### Häufig überschriebene Memberfunktionen der Klasse CDialog\-Klasse  
  
|Memberfunktion|Meldung reagiert es auf|Zweck der Überschreibung|  
|--------------------|-----------------------------|------------------------------|  
|`OnInitDialog`|**WM\_INITDIALOG**|Initialisieren Sie die Steuerelemente des Dialogfelds.|  
|`OnOK`|**BN\_CLICKED** für Schaltfläche **IDOK**|Reagieren, wenn der Benutzer auf die Schaltfläche OK klickt.|  
|`OnCancel`|**BN\_CLICKED** für Schaltfläche **IDCANCEL**|Reagieren, wenn der Benutzer auf die Schaltfläche Abbrechen klickt.|  
  
 `OnInitDialog`, `OnOK` und `OnCancel` sind virtuelle Funktionen.  Um sie zu überschreiben, deklarieren Sie eine überschreibende Funktion in der abgeleiteten Dialogfeldklasse mit [Eigenschaftenfenster](../Topic/Properties%20Window.md).  
  
 `OnInitDialog` wird aufgerufen, bevor das Dialogfeld angezeigt wird.  Sie müssen den Handler der Standard `OnInitDialog` \- Überschreibung normalerweise als die erste Aktion im Handler aufrufen.  Standardmäßig gibt `OnInitDialog`**TRUE** zurück, um anzugeben, dass der Fokus auf das erste Steuerelement im Dialogfeld festgelegt werden sollte.  
  
 `OnOK` wird in der Regel für gleichzeitig jedoch keine modalen Dialogfelder überschrieben.  Wenn Sie diesen Handler für ein modales Dialogfeld überschreiben, rufen Sie die Basisklassenversion von der Überschreibung auf \- dass `EndDialog` \- or\-Aufruf `EndDialog` selbst aufgerufen wird.  
  
 `OnCancel` ist normalerweise für modale Dialogfelder nicht überschrieben.  
  
 Weitere Informationen zu dieser Memberfunktionen, Klasse finden Sie unter [CDialog\-Klasse](../mfc/reference/cdialog-class.md) in der *MFC\-Referenz* und in der Übersicht über [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md).  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)   
 [Häufig hinzugefügte Memberfunktionen](../mfc/commonly-added-member-functions.md)