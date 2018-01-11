---
title: Desktopanwendungen (Visual C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a020b534-293c-44e2-aa48-516c43ddeb8f
caps.latest.revision: "17"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7e2da53a234f63bfd4c8a7f84ec5c107426f0e7c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="desktop-applications-visual-c"></a>Desktopanwendungen (Visual C++)
Ein *Desktopanwendung* in C++ ist eine systemeigene Anwendung, die den vollständigen Satz von Windows-APIs und entweder ausgeführt wird, die in einem Fenster oder in der Systemkonsole zugreifen können. Desktopanwendungen in C++ können unter Windows XP bis Windows 10 ausgeführt werden (Obwohl Windows XP wird nicht mehr offiziell unterstützt, und es gibt viele Windows-APIs, die seitdem eingeführt wurden).   Eine Desktopanwendung unterscheidet sich von einer app für universelle Windows-Plattform (UWP), die auf PCs unter Windows 10 sowie auf XBox, Windows Phone, Surface Hub und anderen Geräten ausgeführt werden kann. Weitere Informationen zu desktop-Visual Studio. Uwp-Apps, finden Sie unter [wählen Sie Ihre Technologiekosten](https://msdn.microsoft.com/en-us/library/windows/desktop/dn614993\(v=vs.85\).aspx).  
  
 **Terminologie**  
  
-   Ein *Win32* Anwendung ist ein Windows-Desktopanwendung in C++, die vornehmen können mithilfe von systemeigenen [C-Windows-APIs und/oder COM APIs](https://msdn.microsoft.com/en-us/library/windows/desktop/ff818516\(v=vs.85\).aspx) CRT und Bibliothek-Standard-APIs und 3rd Party-Bibliotheken. Eine Win32-Anwendung, die in einem Fenster ausgeführt wird erfordert den Entwickler mit Windows-Meldungen in einer Windows-Prozedur-Funktion explizit zu arbeiten. Ungeachtet des Namens kann eine Win32-Anwendung als eine (x86) 32-Bit oder 64-Bit-(x64) binäre kompiliert werden. Die Begriffe X86 und Win32 sind in der Visual Studio-IDE Synonym.  
  
-   Die [Component Object Model (COM)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms694363\(v=vs.85\).aspx) ist eine Spezifikation, die in verschiedenen Sprachen für die Kommunikation mit anderen geschriebene Programme ermöglicht. Viele Windows-Komponenten werden als COM-Objekte implementiert, und führen Sie die standard-COM-Regeln für die objekterstellung, Schnittstelle, die Ermittlung und das Objekt zerstört.  Mithilfe von COM-Objekte von C++-desktopanwendungen ist relativ unkompliziert, aber Schreiben eigener COM-Objekts ist komplexer. Die [Active Template Library (ATL)](../atl/atl-com-desktop-components.md) enthält Makros und Hilfsfunktionen, die COM-Entwicklung zu vereinfachen.  
  
-   Eine MFC-Anwendung ist eine Windows-Desktopanwendung, mit denen die [Microsoft Foundation Classes](../mfc/mfc-desktop-applications.md) auf der Benutzeroberfläche zu erstellen. Eine MFC-Anwendung kann auch COM-Komponenten sowie CRT und Bibliothek-Standard-APIs verwenden. MFC bietet einen dünnen objektorientierten C++-Wrapper über die Nachrichtenschleife für Fenster und die Windows-APIs. MFC ist die Standardauswahl für Anwendungen – insbesondere Enterprise-Anwendungen – die viele Steuerelemente der Benutzeroberfläche oder benutzerdefinierte Steuerelemente haben. MFC stellt bequeme Hilfsklassen für die fensterverwaltung, Serialisierung, Textbearbeitung, Drucken und moderne Benutzeroberflächenelemente wie das Menüband bereit. Mit Win32 vertraut sollte sein, um effektiv mit MFC zu sein.  
  
-   C + c++ / CLI-Anwendung oder Komponente verwendet Erweiterungen für C++-Syntax (wie die C++-Spezifikation nicht zulässig) zur Interaktion zwischen .NET und systemeigener C++-Code zu aktivieren.  C + c++ / CLI-Anwendung kann Teile, die durch systemeigene Funktionen und Komponenten, die auf .NET Framework mit Zugriff auf die Basisklassenbibliothek .NET ausgeführt haben. C + c++ / CLI ist die bevorzugte Option, wenn Sie systemeigenen C++-Code besitzen, muss zum Arbeiten mit Code in c# oder Visual Basic geschrieben wurde. Es dient in erster Linie für die Verwendung in .NET DLLs nicht in Code für die Benutzeroberfläche. Weitere Informationen finden Sie unter [.NET Framework-Programmierung mit C + c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
 Alle Desktopanwendung in C++ können C Runtime (CRT) und die Standardbibliothek Klassen und Funktionen, COM-Objekte und der öffentlichen Windows-Funktionen, die insgesamt als Windows-API bezeichnet werden. Eine Einführung in Windows-Desktopanwendung in C++ finden Sie unter [Erfahren Sie, wie für Windows in C++ programmiert wird](http://go.microsoft.com/fwlink/p/?LinkId=262281).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Konsolenanwendungen](../windows/console-applications-in-visual-cpp.md)|Enthält Informationen über Konsolen-Apps. Eine Win32- oder Win64-Konsolenanwendung hat kein eigenes Fenster und keine Meldungsschleife. Sie wird im Konsolenfenster ausgeführt. Eingaben und Ausgaben werden von der Befehlszeile behandelt.|  
|[Windows-Desktopanwendungen](../windows/windows-desktop-applications-cpp.md)|Wie Sie desktopanwendungen erstellen, die in Windows, im Gegensatz zu der Konsole ausgeführt.|  
|[Ressourcen zum Erstellen eines Spiels mit DirectX (C++)](../windows/resources-for-creating-a-game-using-directx.md)|Links zu Inhalten, zum Erstellen von Spielen in C++.|  
|[Exemplarische Vorgehensweise: Erstellen und Verwenden einer statischen Bibliothek](../windows/walkthrough-creating-and-using-a-static-library-cpp.md)|Vorgehensweise: erstellen eine binären LIB-Datei.|  
|[Gewusst wie: Verwenden des Windows 10-SDKs in einer Windows-Desktopanwendung](../windows/how-to-use-the-windows-10-sdk-in-a-windows-desktop-application.md)|Enthält Schritte zum Einrichten Ihres Projekts für das Erstellen mit dem Windows 10-SDK.|  
  
## <a name="related-articles"></a>Verwandte Artikel  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Windows-Entwicklung](http://go.microsoft.com/fwlink/p/?LinkId=262282)|Enthält Informationen zur Windows-API und COM. (Einige Windows-APIs und Drittanbieter-DLLs werden als COM-Objekte implementiert).|  
|[Hilo: Entwickeln von C++-Anwendungen für Windows 7](http://go.microsoft.com/fwlink/p/?LinkId=262284)|Beschreibt, wie Sie eine vielseitige Windows-Desktopanwendung erstellen, die Windows-Animationen und Direct2D verwendet, um eine karussellbasierte Benutzeroberfläche zu erstellen.  Dieses Lernprogramm wurde nicht aktualisiert wurde, seit Windows 7, aber es bietet weiterhin eine Throough-Einführung in Win32-Programmierung.|  
|[Visual C++](../visual-cpp-in-visual-studio.md)|Beschreibt die wichtigsten Features von Visual C++ in Visual Studio und verlinkt zum Rest der Visual C++-Dokumentation.|  
  
## <a name="see-also"></a>Siehe auch  
 [Visual C++](../visual-cpp-in-visual-studio.md)
