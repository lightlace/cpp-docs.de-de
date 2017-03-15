---
title: "Registrieren von Fensterklassen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WndProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterWndClass-Methode"
  - "Klassen [C++], Registrieren von Fensterklassen"
  - "MFC, Fenster"
  - "Registrieren von Fensterklassen"
  - "Registrierung, Registrieren von Klassen"
  - "Fensterklassen, Registrieren"
  - "WinMain-Methode"
  - "WinMain-Methode, und Registrieren von Fensterklassen"
  - "WndProc-Methode"
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Registrieren von Fensterklassen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fenster "\-" in der herkömmlichen Programmierung für Windows definieren die Eigenschaften einer "Klasse" \(keine C\+\+\-Klasse\) von der eine Zahl Fenster erstellt werden kann.  Diese Art von Klasse ist eine Vorlage oder ein Modell zum Erstellen von Fenstern.  
  
## Fensterklassen\-Registrierung in herkömmlichen Programmen für Windows  
 In herkömmlichen einem Programm für Windows, ohne MFC, verarbeiten Sie alle Meldungen in einem Fenster in der Fensterprozedur "" oder "in **WndProc**." **WndProc** ist ein Fenster mithilfe eines "Fensterklassenregistrierungs" Prozesses zugeordnet.  Im Hauptfenster wird in der Funktion `WinMain` registriert, aber andere Klassen Fenster können überall in der Anwendung registriert sind.  Registrierung hängt von einer Struktur ab, die einen Zeiger auf die **WndProc**\-Funktion zusammen mit Spezifikation für den Cursor, Hintergrundpinsel, z. B. enthält.  Die Struktur wird als Parameter, zusammen mit des Zeichenfolgennamens der Klasse, in einem früheren Aufruf der **RegisterClass**\-Funktion übergeben.  Daher kann eine Registrierungsklasse über mehrere Fenster freigegeben werden.  
  
## Fensterklassen\-Registrierung in MFC\-Programmen  
 Im Gegensatz dazu ist die häufigste Fensterklassenregistrierungsaktivität automatisch in einem MFC\-Framework\-Programm ausgeführt.  Wenn Sie MFC verwenden, leiten Sie normalerweise Fensterklasse eine C\+\+\-Headerdatei aus einer vorhandenen Bibliotheksklasse mit normaler C\+\+\-Syntax für Klassenvererbung.  Das Framework verwendet weiterhin herkömmliche "Registrierungsklassen," und stellt einige Standardzur Verfügung, nach Bedarf registriert für Sie.  Sie können zusätzliche Registrierungsklassen registrieren, indem Sie [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) globale Funktion aufrufen und dann die registrierte Klasse die **Erstellen**\-Memberfunktion `CWnd` übergeben.  Wie, ist die herkömmliche "Registrierungsklasse" in Windows hier beschriebenen nicht mit eine C\+\+\-Klasse verwechselt werden.  
  
 Weitere Informationen finden Sie unter [Technischer Hinweis 1](../mfc/tn001-window-class-registration.md).  
  
## Siehe auch  
 [Erstellen von Fenstern](../mfc/creating-windows.md)