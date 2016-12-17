---
title: "TN070: MFC-Fensterklassennamen"
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
  - "vc.mfc.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN070"
  - "Fensterklassennamen"
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# TN070: MFC-Fensterklassennamen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert.  Daher können einige Verfahren und Themen veraltet oder falsch sein.  Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 MFC\-Fenster verwenden einen dynamisch erstellten Klassennamen, der die Funktionen des Fensters wieder.  MFC generiert Klassennamen dynamisch für Rahmenfenster, Ansichten und die Popupfenster, die von der Anwendung erstellt werden.  Die Dialogfelder und Steuerelemente, die von einer MFC\-Anwendung erstellt werden, weisen den Windows\-angegebenen Namen für die Klasse des Fensters fragliche.  
  
 Sie können den dynamisch bereitgestellten Klassennamen ersetzen, indem Sie eine Fensterklasse registrieren und in einer Überschreibung von [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) verwenden.  die MFC\-angegebenen Klassennamen dort eines der beiden folgenden Formate an:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 Die hexadezimalen Ziffern, die die `%x` Zeichen ersetzen, werden anhand von Daten aus der [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)\-Struktur gefüllt.  MFC verwendet diese Technik ebenfalls, sodass mehrere C\+\+\-Klassen, die identische **WNDCLASS**\-Strukturen benötigen, derselben registrierten Fensterklasse freigeben können.  Anders als die meisten einfachen Win32\-Anwendungen enthalten MFC\-Anwendungen nur ein **WNDPROC**, sodass Sie **WNDCLASS**\-Strukturen leichter freigeben, um Zeit und Speicherplatz zu sparen.  Die austauschbaren Werte für die `%x` Zeichen, die oben angezeigt werden, sind, wie folgt:  
  
-   **WNDCLASS.hInstance**  
  
-   **WNDCLASS.style**  
  
-   **WNDCLASS.hCursor**  
  
-   **WNDCLASS.hbrBackground**  
  
-   **WNDCLASS.hIcon**  
  
 Das erste Formular \(`Afx:%x:%x`\) wird verwendet, wenn **hCursor**, **hbrBackground** und **hIcon** alle **NULL** sind.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)   
 [TN020: ID\-Benennungs\- und Nummerierungskonventionen](../mfc/tn020-id-naming-and-numbering-conventions.md)