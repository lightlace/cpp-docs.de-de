---
title: "Erstellen eines nicht modalen Eigenschaftenblatts"
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
  - "Create-Methode [C++], Eigenschaftenblätter"
  - "nicht modulare Eigenschaftenblätter"
  - "Eigenschaftenblätter, Nicht modal"
ms.assetid: eafd8a92-cc67-4a69-a5fb-742c920d1ae8
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen eines nicht modalen Eigenschaftenblatts
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Normalerweise sind die Eigenschaftenblätter, die Sie erstellen, modal.  Wenn ein modales Eigenschaftenblatt verwendet, vor der Anwendung eines anderen Teils der Anwendung der Benutzer muss das Eigenschaftenblatt schließen.  Dieser Artikel werden Methoden beschrieben, die Sie verwenden können, um ein nicht modales Eigenschaftenblatt zu erstellen, das dem Benutzer ermöglicht, um das Eigenschaftenblatt geöffnet zu führen bei der Anwendung andere Teile der Anwendung.  
  
 Um ein Eigenschaftenblatt als nicht modales Dialogfeld als nicht modales Dialogfeld anzuzeigen, rufen Sie [CPropertySheet::Create](../Topic/CPropertySheet::Create.md) anstelle von [DoModal](../Topic/CPropertySheet::DoModal.md) auf.  Sie müssen einige zusätzliche Aufgaben ebenfalls implementieren, ein nicht modales Eigenschaftenblatt zu unterstützen.  
  
 Eine der zusätzlichen Aufgaben ist dem Austausch von Daten zwischen dem Eigenschaftenblatt und dem externen Objekt, die es verändert, wann das Eigenschaftenblatt geöffnet ist.  Dies ist im Allgemeinen dieselbe Aufgabe wie für Standardnicht modal dialogfelder.  Der Rahmen dieser Aufgabe implementiert einen Channel der Kommunikation zwischen nicht modalen Eigenschaftenblatt und dem externen Objekt, auf die die Eigenschafteneinstellungen gelten.  Diese Implementierung ist deutlich einfacher, wenn Sie eine Klasse von [CPropertySheet](../mfc/reference/cpropertysheet-class.md) für das nicht modales Eigenschaftenblatt berechnen.  Dieser Artikel wird vorausgesetzt, dass Sie getan haben.  
  
 Eine Methode für die Kommunikation zwischen dem nicht modalen Eigenschaftenblatt und dem externen Objekt \(die aktuelle Auswahl in einer Ansicht\), ist, einen Zeiger aus dem Eigenschaftenblatt für das externe Objekt zu definieren.  Definieren einer Funktion aufgerufen \(etwa `SetMyExternalObject`\) in `CPropertySheet` abgeleitete Klasse, um den der Zeiger zu ändern, wenn der Fokus von einem externen Objekt in einen anderen ändert.  Die `SetMyExternalObject`\-Funktion muss die Einstellungen zurücksetzen, damit jede Eigenschaftenseite das neu ausgewählte externe Objekt übernommen.  Um dies zu erreichen, muss die Funktion `SetMyExternalObject` in der Lage sein auf die [CPropertyPage](../mfc/reference/cpropertypage-class.md)\-Objekte zugreifen, die der `CPropertySheet`\-Klasse gehören.  
  
 Die bequemste Methode, Zugriff auf den Eigenschaftenseiten innerhalb eines Eigenschaftenblatts zu ermöglichen, ist die `CPropertyPage`\-Objekte in `CPropertySheet` abgeleitetes Objekt.  Das Einbetten `CPropertyPage`\-Objekts in ein `CPropertySheet`\- abgeleitetes Objekt unterscheidet sich vom herkömmlichen Entwurf für modale Dialogfelder, deren Besitzer des Eigenschaftenblatts die `CPropertyPage`\-Objekte erstellt und sie zum Eigenschaftenblatt zu [CPropertySheet::AddPage](../Topic/CPropertySheet::AddPage.md) führt.  
  
 Es gibt viele Benutzeroberflächealternativen für Situationen, wenn die Einstellungen des nicht modalen Eigenschaftenblatts zu einem externen Objekt angewendet werden sollen.  Eine Alternative besteht darin, die Einstellungen der aktuellen Seite angewendet, wenn der Benutzer einen beliebigen Wert ändert.  Eine Alternative besteht darin, eine übernehmensschaltfläche bereitzustellen, die dem Benutzer ermöglicht, Änderungen auf den Eigenschaftenseiten der Animation, bevor sie für das externe Objekt übergibt.  Informationen zu Möglichkeiten, die übernehmensschaltfläche zu behandeln, finden Sie im Artikel [Behandeln der übernehmens\-Schaltfläche](../mfc/handling-the-apply-button.md).  
  
## Siehe auch  
 [Eigenschaftenblätter](../mfc/property-sheets-mfc.md)   
 [Datenaustausch](../mfc/exchanging-data.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)