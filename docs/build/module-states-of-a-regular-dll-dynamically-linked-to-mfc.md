---
title: "Modulzust&#228;nde einer regul&#228;ren, dynamisch mit MFC verkn&#252;pften DLL"
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
  - "DLLs [C++], Modulzustände"
  - "MFC-DLLs [C++], Reguläre DLLs"
  - "Modulzustände [C++]"
  - "Modulzustände [C++], Reguläre DLLs – dynamisch verknüpft mit"
  - "Reguläre DLLs [C++], Dynamisch verknüpft mit MFC"
ms.assetid: b4493e79-d25e-4b7f-a565-60de5b32c723
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Modulzust&#228;nde einer regul&#228;ren, dynamisch mit MFC verkn&#252;pften DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie haben die Möglichkeit, eine reguläre DLL dynamisch mit einer MFC\-DLL zu verknüpfen und auf diese Weise sehr komplizierte Konfigurationen zu erstellen.  Eine reguläre DLL und die ausführbare Datei, die die DLL verwendet, können z. B. beide dynamisch mit der MFC\-DLL und beliebigen Erweiterungs\-DLLs verknüpft werden.  
  
 Mit dieser Konfiguration ergibt sich ein Problem in Hinblick auf die globalen MFC\-Daten wie den Zeiger auf das aktuelle `CWinApp`\-Objekt und Handlezuordnungen.  
  
 In früheren Versionen als MFC Version 4.0 werden diese globalen Daten in der MFC\-DLL selbst gespeichert und von allen Modulen im Prozess gemeinsam genutzt.  Da jeder Prozess, der eine Win32\-DLL verwendet, über eine eigene Kopie der Daten in der DLL verfügt, wird durch dieses Schema eine einfache Möglichkeit zum Nachverfolgen prozessspezifischer Daten bereitgestellt.  Darüber hinaus können diese Elemente in der MFC\-DLL selbst nachverfolgt werden, da das AFXDLL\-Modell davon ausgeht, dass nur ein `CWinApp`\-Objekt und nur ein Satz von Handlezuordnungen im Prozess vorhanden sind.  
  
 Durch die Möglichkeit, eine reguläre DLL dynamisch mit der MFC\-DLL zu verknüpfen, ist es mittlerweile möglich, dass zwei oder mehr `CWinApp`\-Objekte und auch zwei oder mehr Sets von Handlezuordnungen in einem Prozess vorhanden sind.  Wie entscheidet nun MFC, welche davon verwendet werden sollen?  
  
 Die Lösung besteht darin, für jedes Modul \(Anwendung oder reguläre DLL\) eine eigene Kopie dieser globalen Zustandsinformationen bereitzustellen.  Auf diese Weise wird durch den Aufruf von  `in der regulären DLL ein Zeiger auf das CWinApp`\-Objekt in der DLL zurückgegeben und nicht auf das in der ausführbaren Datei.  Diese modulspezifische Kopie der globalen MFC\-Daten wird als "Modulzustand" bezeichnet. Eine Beschreibung finden Sie im [technischen Hinweis 58 zu MFC](../mfc/tn058-mfc-module-state-implementation.md).  
  
 Die allgemeine MFC\-Fensterprozedur wechselt automatisch zum korrekten Modulzustand, sodass dieser Umstand nicht in den Meldungshandlern berücksichtigt werden muss, die in der regulären DLL implementiert sind.  Wenn jedoch die ausführbare Datei einen Aufruf in der regulären DLL vornimmt, müssen Sie den aktuellen Modulzustand explizit auf den Zustand der DLL setzen.  Sie verwenden dazu in jeder aus der DLL exportierten Funktion das `AFX_MANAGE_STATE`\-Makro.  Fügen Sie zu diesem Zweck die folgende Codezeile am Anfang der aus der DLL exportierten Funktionen ein:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState( ))  
```  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Verwalten der Statusdaten von MFC\-Modulen](../mfc/managing-the-state-data-of-mfc-modules.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Erweiterungs\-DLLs](../build/extension-dlls-overview.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)