---
title: "Gibt es MFC-Klassen oder -Funktionen, die nicht in einer MFC-DLL verwendet werden k&#246;nnen?"
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
  - "DLLs [C++], MFC"
  - "DLLs [C++], Beschränkungen"
  - "MFC-DLLs [C++], Beschränkungen"
ms.assetid: 18e2f1cb-4f72-4d3a-a951-3488208872c7
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Gibt es MFC-Klassen oder -Funktionen, die nicht in einer MFC-DLL verwendet werden k&#246;nnen?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erweiterungs\-DLLs verwenden die von `CWinApp` abgeleitete Klasse der Clientanwendung.  Sie dürfen keine eigene, von `CWinApp` abgeleitete Klasse haben.  
  
 Reguläre DLLs müssen über eine von `CWinApp` abgeleitete Klasse sowie über ein einzelnes Objekt dieser Anwendungsklasse verfügen, wie dies auch bei einer MFC\-Anwendung der Fall ist.  Anders als das `CWinApp`\-Objekt einer Anwendung hat das `CWinApp`\-Objekt der DLL keine Haupt\-Meldungsverteilschleife.  
  
 Da der `CWinApp::Run`\-Mechanismus nicht auf eine DLL angewendet werden kann, ist die Haupt\-Meldungsverteilschleife im Besitz der Anwendung.  Wenn die DLL nicht modale Dialogfelder öffnet oder ein eigenes Hauptrahmenfenster besitzt, dann muss die Haupt\-Meldungsverteilschleife der Anwendung eine von der DLL exportierte Routine aufrufen, die wiederum die Memberfunktion `CWinApp::PreTranslateMessage` des DLL\-Anwendungsobjekts aufruft.  
  
## Siehe auch  
 [FAQ \(Häufig gestellte Fragen\) zu DLLs](../build/dll-frequently-asked-questions.md)