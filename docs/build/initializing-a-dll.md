---
title: "Initialisieren einer DLL | Microsoft Docs"
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
  - "DLLs [C++], Initialisieren"
  - "Initialisieren von DLLs"
  - "Terminierungscode [C++]"
ms.assetid: f655c5ff-ab5b-493a-a1da-4d1074e60c5b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Initialisieren einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In der Regel verfügt die DLL über Initialisierungscode \(wie dem zur Speicherbelegung\), der beim Laden der DLL ausgeführt werden muss.  Bei Verwendung von Visual C\+\+ hängt es von der Art der erstellten DLL ab, an welcher Stelle Sie den Initialisierungscode einfügen.  Wenn Sie keinen Initialisierungs\- oder Terminierungscode hinzufügen müssen, sind beim Erstellen der DLL keine besonderen Schritte erforderlich.  Falls die DLL jedoch initialisiert werden muss, können Sie der folgenden Tabelle entnehmen, wo Code eingefügt werden muss.  
  
|DLL\-Typ|Wo Initialisierungs\- und Terminierungscode eingefügt werden muss|  
|--------------|-----------------------------------------------------------------------|  
|Reguläre DLL|In den Funktionen `InitInstance` und `ExitInstance` des `CWinApp`\-Objekts der DLL.|  
|Erweiterungs\-DLL|In der vom MFC\-DLL\-Assistenten generierten `DllMain`\-Funktion.|  
|MFC\-fremde DLL|In einer Funktion mit dem Namen `DllMain`, die von Ihnen bereitgestellt wird.|  
  
 In Win32 können alle DLLs eine optionale Einstiegspunktfunktion \(in der Regel `DllMain`\) enthalten, die sowohl für die Initialisierung als auch für die Terminierung aufgerufen wird.  Dadurch haben Sie die Möglichkeit, zusätzliche Ressourcen je nach Bedarf zu reservieren oder freizugeben.  Windows ruft die Einstiegspunktfunktion in den folgenden vier Situationen auf: Anfügen an bzw. Trennen von einem Prozess und Anfügen an einen bzw. Trennen von einem Thread.  
  
 Die C\-Laufzeitbibliothek stellt eine Einstiegspunktfunktion mit dem Namen **\_DllMainCRTStartup** bereit, durch die `DllMain` aufgerufen wird.  Abhängig vom DLL\-Typ sollte entweder im Quellcode eine Funktion mit dem Namen `DllMain` enthalten sein, oder Sie sollten die in der MFC\-Bibliothek vorhandene `DllMain`\-Funktion verwenden.  
  
## Was möchten Sie tun?  
  
-   [Reguläre DLLs initialisieren](../build/initializing-regular-dlls.md)  
  
-   [Erweiterungs\-DLLs initialisieren](../build/initializing-extension-dlls.md)  
  
-   [MFC\-fremde DLLs initialisieren](../build/initializing-non-mfc-dlls.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Das Verhalten der C\-Laufzeitbibliothek und \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [\<caps:sentence id\="tgt24" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>Die Funktionsspezifikation für DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt25" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic Link Library\-Einstiegspunktfunktion \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)