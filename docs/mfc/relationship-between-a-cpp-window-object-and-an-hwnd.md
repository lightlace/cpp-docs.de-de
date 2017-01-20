---
title: "Beziehung zwischen einem C++-Fensterobjekt und einem HWND"
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
  - "HWND"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWnd-Klasse, HWND"
  - "HWND"
  - "HWND, Fensterobjekte"
  - "Fensterobjekte [C++], HWND und"
  - "Windows-Fenster [C++]"
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Beziehung zwischen einem C++-Fensterobjekt und einem HWND
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Window\-Objekt ist ein Objekt der Klasse C\+\+ `CWnd` \(oder der abgeleiteten Klasse\) die Programmerstellung direkt erstellt.  Es kommt und wechselt in Reaktion auf Konstruktor\- und Destruktoraufrufe des Programms.  Das Windows\-Fenster hingegen ist ein nicht transparentes Handle einer internen Windows\-Datenstruktur, die an ein Fenster entspricht und nutzt Systemressourcen falls vorhanden.  Ein Windows\-Fenster wird durch ein "Fensterhandle" \(`HWND`\) identifiziert und wird erstellt, nachdem das `CWnd`\-Objekt durch einen Aufruf der **Erstellen**\-Memberfunktion der Klasse `CWnd` erstellt wird.  Das Fenster wird entweder durch einen Programmaufruf oder durch eine Aktion des Benutzers zerstört werden.  Das Fensterhandle wird `m_hWnd` in der Membervariable des Fensterobjekts gespeichert.  Die folgende Abbildung zeigt die Beziehung zwischen dem C\+\+\-Fensterobjekt und das Windows\-Fenster an.  Fenster erstellen, werden in [Erstellen von Windows](../mfc/creating-windows.md) erläutert.  Fenster Löschen eines Auflistungsobjekts, werden in [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md) erläutert.  
  
 ![CWnd&#45;Fensterobjekt und resultierendes Fenster](../mfc/media/vc37fj1.png "vc37FJ1")  
window\-Objekt und Windows\-Fenster  
  
## Siehe auch  
 [Fensterobjekte](../mfc/window-objects.md)