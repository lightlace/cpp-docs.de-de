---
title: "Namenskonventionen f&#252;r MFC-DLLs | Microsoft Docs"
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
  - "DLLs [C++], Bibliotheknamen"
  - "DLLs [C++], Benennungskonventionen"
  - "Bibliotheken [C++], MFC-DLL-Namen"
  - "MFC-DLLs [C++], Benennungskonventionen"
  - "MFC-Bibliotheken [C++], Benennungskonventionen"
  - "Benennungskonventionen [C++], MFC-DLLs"
  - "Gemeinsam genutzte DLL-Versionen [C++]"
ms.assetid: 0db9c3f3-87d3-40e8-8964-250f9d2a2209
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Namenskonventionen f&#252;r MFC-DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die in MFC enthaltenen DLLs und Bibliotheken sind gemäß einer strukturierten Namenskonvention benannt.  Auf diese Weise ist leichter erkennbar, welche DLL oder Bibliothek für welchen Zweck verwendet werden sollte.  
  
 Die Importbibliotheken, die zum Erstellen von Anwendungen oder Erweiterungs\-DLLs erforderlich sind, die diese DLLs verwenden, verfügen über denselben Basisnamen wie die DLL, haben jedoch die Dateinamenerweiterung .lib.  
  
### Namenskonvention für gemeinsam genutzte DLLs  
  
|DLL|**Beschreibung**|  
|---------|----------------------|  
|MFCx0.DLL|MFC\-DLL, ANSI\-Releasebuild|  
|MFCx0U.DLL|MFC\-DLL, Unicode\-Releasebuild|  
|MFCx0D.DLL|MFC\-DLL, ANSI\-Debugbuild|  
|MFCx0UD.DLL|MFC\-DLL, Unicode\-Debugbuild|  
  
 Wenn Sie die gemeinsam genutzte MFC\-DLL\-Version dynamisch verknüpfen, sei es aus einer Anwendung heraus oder aus einer Erweiterungs\-DLL, dann müssen Sie **MFCx0.DLL** in Ihr Produkt einschließen.  Wenn Sie Unicode\-Unterstützung in Ihre Anwendung implementieren, schließen Sie stattdessen **MFCx0U.DLL** ein.  
  
 Wenn Sie die DLL statisch mit MFC verknüpfen, müssen Sie diese mit einer der statischen MFC\-Bibliotheken verknüpfen.  Diese Versionen werden entsprechend der Konvention \[N&#124;U\]AFXCW\[D\].LIB benannt.  Weitere Informationen finden Sie in der Tabelle "Namenskonventionen Static Link Libraries" unter [Namenskonventionen für Bibliotheken](../mfc/library-naming-conventions.md) \(MFC\).  
  
 Eine Liste der Visual C\+\+\-DLLs, die Sie mit Ihren Anwendungen verteilen können, finden Sie in der Datei Redist.txt in Ihrer Visual Studio\-Installation.  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Namenskonventionen für Bibliotheken](../mfc/library-naming-conventions.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)