---
title: "Windows-Desktopanwendungen (Visual C++)"
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
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: 17
caps.handback.revision: "12"
ms.author: "ghogen"
manager: "ghogen"
---
# Windows-Desktopanwendungen (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können eine Windows\-Desktopanwendung erstellen, wenn Sie eine systemeigene Desktopanwendung erstellen möchten, die eine fensterbasierte Benutzeroberfläche hat und unter Windows\-Versionen von Windows XP bis Windows 10 auf dem Windows\-Desktop ausgeführt werden kann.  
  
 *Windows\-Desktopanwendung* \(in älterer Literatur auch als Win32\-Anwendung bezeichnet\) ist der herkömmliche Begriff für eine Anwendung, die Windows\-Meldungen direkt mit Meldungsschleifen verarbeitet, anstatt ein Framework wie Microsoft Foundation Classes \(MFC\), Active Template Library \(ATL\) oder .NET Framework zu verwenden. Eine Windows\-Desktopanwendung in C\+\+ kann CRT\- \(C Runtime\) und STL\-Klassen \(Standard Template Library\) und \-Funktionen, COM\-Objekte sowie jede der öffentlichen Windows\-Funktionen verwenden, die insgesamt als Windows\-API bezeichnet werden. Eine Einführung in Windows\-Desktopanwendung in C\+\+ finden Sie unter [Erfahren Sie, wie für Windows in C\+\+ programmiert wird](http://go.microsoft.com/fwlink/p/?LinkId=262281).  
  
 Eine Windows\-Desktopanwendung ist eine Möglichkeit, eine systemeigene Desktopanwendung für Windows zu erstellen; die andere Methode ist eine MFC\-Anwendung. MFC ist die Standardauswahl für Apps, insbesondere für Unternehmens\-Apps, die viele benutzerdefinierte Steuerelemente oder Benutzersteuerelemente haben. MFC stellt bequeme Hilfsklassen für die Serialisierung, Textbearbeitung und das Drucken sowie moderne Benutzeroberflächenelemente wie das Menüband bereit. Diese Klassen sind für eine Windows\-Desktopanwendung nicht verfügbar.  
  
## Verwandte Artikel  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Windows\-Entwicklung](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Enthält Informationen zur Windows\-API und COM. \(Einige Windows\-APIs und Drittanbieter\-DLLs werden als COM\-Objekte implementiert\).|  
|[Hilo: Entwickeln von C\+\+\-Anwendungen für Windows 7](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Beschreibt, wie Sie eine vielseitige Windows\-Desktopanwendung erstellen, die Windows\-Animationen und Direct2D verwendet, um eine karussellbasierte Benutzeroberfläche zu erstellen.|  
|[Konsolenanwendungen](../windows/console-applications-in-visual-cpp.md)|Enthält Informationen über Konsolen\-Apps. Eine Win32\- oder Win64\-Konsolenanwendung hat kein eigenes Fenster und keine Meldungsschleife. Sie wird im Konsolenfenster ausgeführt. Eingaben und Ausgaben werden von der Befehlszeile behandelt.|  
|[Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)|Beschreibt die wichtigsten Features von Visual C\+\+ in Visual Studio und verlinkt zum Rest der Visual C\+\+\-Dokumentation.|  
|[Visual C\+\+ Developer Center](http://go.microsoft.com/fwlink/p/?LinkId=252885) auf der MSDN\-Website|Enthält Lernprogramme, Blogbeiträge und Artikel, die für Windows\-Desktopanwendungen relevant sind.|  
|[Gewusst wie: Verwenden des Windows 10\-SDKs in einer Windows\-Desktopanwendung](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Enthält Schritte zum Einrichten Ihres Projekts für das Erstellen mit dem Windows 10\-SDK.|