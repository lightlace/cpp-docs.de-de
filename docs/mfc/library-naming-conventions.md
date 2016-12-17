---
title: "Bibliotheks-Benennungskonventionen"
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
  - "Codekonventionen, MFC-Bibliotheknamen"
  - "Konsolenanwendungen, MFC-Bibliotheksversionen"
  - "Konventionen [C++], MFC-Bibliotheknamen"
  - "Bibliotheken [C++], Statische"
  - "MFC-Bibliotheken, Benennungskonventionen"
  - "NAFXCW.LIB"
  - "NAFXCWD.LIB"
  - "Benennungskonventionen [C++], MFC-Objektcodebibliotheken"
  - "Objektcodebibliotheken"
  - "Objektcodebibliotheken, MFC-Benennungskonventionen"
ms.assetid: 39fe7d93-5a14-4c6a-b16c-bf318fa01278
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Bibliotheks-Benennungskonventionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Objektcodebibliotheken für MFC verwenden die folgenden Namenskonventionen.  Die Bibliotheksnamen haben das Formular  
  
 *uAFX* W .LIB `d``c`  
  
 wobei die Buchstaben, die in der Schriftschnitt Kleinbuchstaben angezeigt werden, sind, Thread\- Platzhalter für Bezeichner, deren Bedeutung im Folgenden dargestellt werden:  
  
### Bibliotheks\-Namenskonventionen  
  
|Bezeichner|Werte und Bedeutung|  
|----------------|-------------------------|  
|*u*|ANSI \(n\) oder Unicode \(U\)|  
|`c`|Art des Programms zu erstellen: C\=all|  
|`d`|Debuggen Sie oder geben Sie frei: D\=Debug; Lassen Sie Bezeichner für Version weg|  
  
 Der Standardwert ist eine Anwendung, Debug\- Windows ANSI für die Intel\-Plattform zu erstellen: NAFXCWD.Lib.  Alle Bibliotheken, die in der folgenden Tabelle aufgeführt sind, befinden sich vordefiniert im Verzeichnis \\atlmfc\\lib auf der Visual C\+\+\-CD\-ROM.  
  
### Namenskonventionen Static Link Libraries  
  
|Bibliothek|**Beschreibung**|  
|----------------|----------------------|  
|NAFXCW.LIB|MFC\-STATIC\-Link\-Bibliothek Releaseversion,|  
|NAFXCWD.LIB|MFC\-STATIC\-Link\-Bibliothek, Debugversion|  
|UAFXCW.LIB|MFC\-STATIC\-Link\-Bibliothek mit Unicode\-Unterstützung Releaseversion,|  
|UAFXCWD.LIB|MFC\-STATIC\-Link\-Bibliothek mit Unicode\-Unterstützung, Debugversion|  
  
> [!NOTE]
>  Wenn Sie eine Bibliotheksversion erstellen müssen, finden Sie die Infodateidatei im Verzeichnis \\atlmfc\\src\\mfc.  Diese Datei beschreibt, die angegebene Makefile mit NMAKE zu verwenden.  
  
 Weitere Informationen finden Sie unter [Namenskonventionen für MFC\-DLLs](../build/naming-conventions-for-mfc-dlls.md) und [Unicode\-Versionen der MFC\-Bibliotheken](../mfc/unicode-in-mfc.md).  
  
## Siehe auch  
 [MFC\-Bibliotheksversionen](../mfc/mfc-library-versions.md)