---
title: "Allgemeine Ablauffolge bei der Fenstererstellung | Microsoft Docs"
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
  - "Rahmenfenster [C++], Erstellen"
  - "Reihenfolge [C++]"
  - "Reihenfolge [C++], Fenstererstellung"
  - "Fenster [C++], Erstellen"
ms.assetid: 9cd8c7ea-5e24-429e-b6d9-d7b6041d8ba6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Allgemeine Ablauffolge bei der Fenstererstellung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie ein Fenster von Ihrem erstellen, verwendet z Auch, untergeordnetes Fenster, dem Framework viel den gleichen Prozess wie das, das in [Dokument\/Ansichts\-Erstellung](../mfc/document-view-creation.md) beschrieben wird.  
  
 Alle Fensterklassen, die von MFC bereitgestellte werden, legen [Konstruktion zweistufige](../mfc/one-stage-and-two-stage-construction-of-objects.md).  Das heißt, während eines Aufrufs des Operators C\+\+ **neu**, wird der Konstruktor auf und initialisiert, ein C\+\+\-Objekt stellt jedoch kein entsprechendes Windows\-Fenster erstellt.  Das wird danach durchgeführt, indem die [Erstellen](../Topic/CWnd::Create.md)\-Memberfunktion des Fensterobjekts aufruft.  
  
 Die **Erstellen**\-Memberfunktion stellt das Windows\-Fenster erstellt und speichert seine `HWND` im öffentlichen Datenmember [m\_hWnd](../Topic/CWnd::m_hWnd.md) des C\+\+\-Objekts.  **Erstellen** gibt vollständige Flexibilität zum Erstellungsparametern.  Bevor Sie **Erstellen** aufrufen, können Sie eine Fensterklasse mit der globalen Funktion [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) registrieren, um das Symbol festzulegen und Klasse formatiert für denjenigen Frame.  
  
 Für Rahmenfenster können Sie die Memberfunktion [LoadFrame](../Topic/CFrameWnd::LoadFrame.md) statt **Erstellen** verwenden.  `LoadFrame` stellt das Windows\-Fenster mit wenig Parameter erstellt.  Sie ruft viele Standardwerte von Ressourcen, einschließlich die Beschriftung der Frame, das Symbol\-, die Zugriffstastentabelle und das Menü ab.  
  
> [!NOTE]
>  das Symbol, Zugriffstastentabelle und Menüressourcen müssen eine allgemeine Ressourcen\-ID, wie **IDR\_MAINFRAME** verfügen, damit sie von LoadFrame geladen werden können.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Fensterobjekte](../mfc/window-objects.md)  
  
-   [Das Registrieren des Fensters "Klasse"](../mfc/registering-window-classes.md)  
  
-   [Zerstören von Fensterobjekten](../mfc/destroying-window-objects.md)  
  
-   [Erstellen von Dokumentrahmenfenstern](../mfc/creating-document-frame-windows.md)  
  
## Siehe auch  
 [Erstellen von Fenstern](../mfc/creating-windows.md)