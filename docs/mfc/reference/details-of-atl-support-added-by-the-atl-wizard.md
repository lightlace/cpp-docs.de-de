---
title: "Details zur ATL-Unterst&#252;tzung, die vom ATL-Assistenten hinzugef&#252;gt wird"
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
  - "vc.codewiz.atl.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, MFC-Projekte"
  - "MFC, ATL-Unterstützung"
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Details zur ATL-Unterst&#252;tzung, die vom ATL-Assistenten hinzugef&#252;gt wird
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wenn Sie einer [vorhandenen MFC\-Anwendung oder DLL ATL\-Unterstützung hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), nimmt Visual C\+\+ die folgenden Änderungen am vorhandenen MFC\-Projekt vor \(das Projekt in diesem Beispiel heißt `MFCEXE`\):  
  
-   Es werden zwei neue Dateien hinzugefügt \(eine IDL\-Datei und eine RGS\-Datei, die zur Serverregistrierung verwendet werden\).  
  
-   Der Headerdatei und der Implementierungsdatei der Hauptanwendung \(**Mfcexe.h** und **Mfcexe.cpp**\) wird eine neue \(von **CAtlMFCModule** abgeleitete\) Klasse hinzugefügt.  Zusätzlich zur neuen Klasse wird `InitInstance` Registrierungscode hinzugefügt.  Außerdem wird der `ExitInstance`\-Funktion Code hinzugefügt, um die Erstellung des Klassenobjekts zu widerrufen.  Schließlich werden der Implementierungsdatei zwei neue Headerdateien \(**Initguid.h** und **Mfcexe\_i.c**\) hinzugefügt, durch die die neuen GUIDs für die von **CAtlMFCModule** abgeleitete Klasse deklariert und initialisiert werden.  
  
-   Um den Server ordnungsgemäß zu registrieren, wird der Ressourcendatei des Projekts ein Eintrag für die neue RGS\-Datei hinzugefügt.  
  
## Hinweise zu DLL\-Projekten  
 Wenn Sie einem MFC\-DLL\-Projekt ATL\-Unterstützung hinzufügen, werden Sie einige Unterschiede feststellen.  Den Funktionen **DLLRegisterServer** und **DLLUnregisterServer** wird Code hinzugefügt, durch den die DLL registriert bzw. deren Registrierung aufgehoben werden kann.  Außerdem wird den Funktionen [DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md) und [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md) Code hinzugefügt.  
  
## Siehe auch  
 [ATL\-Unterstützung in einem MFC\-Projekt](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Hinzufügen neuer Funktionen mit Code\-Assistenten](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Hinzufügen einer Memberfunktion](../../ide/adding-a-member-function-visual-cpp.md)   
 [Hinzufügen einer Membervariablen](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Überschreiben einer virtuellen Funktion](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC\-Meldungshandler](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigieren in der Klassenstruktur](../../ide/navigating-the-class-structure-visual-cpp.md)