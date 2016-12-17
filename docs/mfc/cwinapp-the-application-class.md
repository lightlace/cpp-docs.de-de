---
title: "CWinApp: Die Anwendungsklasse"
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
  - "CWinApp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "application-Klasse"
  - "CWinApp-Klasse, CWinThread"
  - "CWinApp-Klasse, Multithreading"
  - "CWinApp-Klasse, WinMain"
  - "CWinThread-Klasse, und CWinApp"
  - "InitApplication-Methode"
  - "MFC [C++], WinMain und"
  - "WinMain-Methode"
  - "WinMain-Methode, in MFC"
ms.assetid: 935822bb-d463-481b-a5f6-9719d68ed1d5
caps.latest.revision: 13
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CWinApp: Die Anwendungsklasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Hauptanwendungsklasse in MFC kapselt die Initialisierung, die die Ausführung und das Ende eine Anwendung für das Windows\-Betriebssystem.  Eine Anwendung, die im Framework erstellt wird, darf nur ein Objekt eine Klasse verfügen, die von [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitet wird.  Dieses Objekt wird erstellt, bevor Fenster erstellt wurden.  
  
 `CWinApp` ist von `CWinThread` abgeleitet, das darstellt den Hauptthread der Ausführung der Anwendung ist, die möglicherweise eine oder mehrere Threads.  In neueren Versionen von MFC, sind `InitInstance`, **Ausführen**, `ExitInstance` und `OnIdle`\-Memberfunktionen tatsächlich in Klasse `CWinThread`.  Diese Funktionen werden hier erläutert, als ob ihnen `CWinApp` stattdessen Member wurden, da die Diskussion die Rolle des Objekts als Anwendungsobjekt anstatt primären Thread bezieht.  
  
> [!NOTE]
>  die Anwendungsklasse setzt den primären Thread der Anwendung der Ausführung fest.  Mithilfe von Win32\-API\-Funktionen können Sie sekundären Threads der Ausführung auch erstellen.  Diese Threads können die MFC\-Bibliothek verwenden.  Weitere Informationen finden Sie unter [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 Wie jedes Programm für das Windows\-Betriebssystem, hat die `WinMain` Framework\-Anwendung eine Funktion.  In einer Framework\-Anwendung jedoch schreiben Sie `WinMain` nicht.  Sie wird von der Klassenbibliothek angegeben und wird aufgerufen, beim Starten.  `WinMain` stellt Standarddienstleistungen wie Registrieren von Fensterklassen.  Sie ruft dann Memberfunktionen des DLL\-Anwendungsobjekts auf, um die Anwendung zu initialisieren und auszuführen. \(Sie können `WinMain` anpassen, indem Sie die `CWinApp`\-Memberfunktionen, überschreiben die `WinMain` aufgerufen wird\).  
  
 Um die Anwendung zu initialisieren, ruft `WinMain` und `InitApplication``InitInstance`\-Memberfunktionen des DLL\-Anwendungsobjekts auf.  Um die Meldungsschleife der Anwendung auszuführen, ruft `WinMain` die **Ausführen**\-Memberfunktion auf.  Bei Beendigung ruft `WinMain` die `ExitInstance`\-Memberfunktion des DLL\-Anwendungsobjekts auf.  
  
> [!NOTE]
>  Die Namen, die in **bold** in dieser Dokumentation angezeigt werden, geben die Elemente an, die von der Microsoft Foundation Class\-Bibliothek und Visual C\+\+ bereitgestellt werden.  Die Namen, die in `monospaced`\-Typ dargestellt werden, geben an Elementen, die Sie erstellen oder überschreiben.  
  
## Siehe auch  
 [Allgemeine MFC\-Themen](../mfc/general-mfc-topics.md)   
 [CWinApp und der MFC\-Anwendungs\-Assistent](../mfc/cwinapp-and-the-mfc-application-wizard.md)   
 [Überschreibbare CWinApp\-Memberfunktionen](../mfc/overridable-cwinapp-member-functions.md)   
 [Spezielle CWinApp\-Dienste](../mfc/special-cwinapp-services.md)