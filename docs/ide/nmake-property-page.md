---
title: Eigenschaftenseite "NMake" (Windows C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- VC.Project.VCNMakeTool.ReBuildCommandLine
- VC.Project.VCNMakeTool.CleanCommandLine
- VC.Project.VCNMakeTool.Output
- VC.Project.VCNMakeTool.BuildCommandLine
dev_langs:
- C++
helpviewer_keywords:
- NMake property page
ms.assetid: bd20cb52-9f1d-4240-b4fc-4f43205ac94b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f156d69467f00c4c4a62ec84d3b870e2999d7115
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-property-page"></a>NMake (Eigenschaftenseite)
Die **NMake** Eigenschaftenseite können Sie die Buildeinstellungen für NMake-Projekte angeben.  
  
 Weitere Informationen über NMake-Projekte finden Sie unter [Erstellen eines Makefile-Projekts](../ide/creating-a-makefile-project.md). Non_Windows MakeFile-Projekte, finden Sie unter [MakeFile-Projekteigenschaften (Linux C++)](../linux/prop-pages/makefile-linux.md), [allgemeine Projekteigenschaften (Android C++-Makefile)](/visualstudio/cross-platform/general-makefile-android-prop-page) oder [NMake-Eigenschaften (Android C++)](/visualstudio/cross-platform/nmake-android-prop-page).
  
 Die **NMake** Eigenschaftenseite enthält die folgenden Eigenschaften.  
  
## <a name="uielement-list"></a>UIElement-Liste  
 **Erstellen Sie über die Befehlszeile**  
 Gibt den Befehl ausgeführt werden, wenn sein **erstellen** geklickt wird, auf die **erstellen** Menü.  
  
 **Erstellen Sie alle über die Befehlszeile neu.**  
 Gibt den Befehl ausgeführt werden, wenn sein **Rebuild All** geklickt wird, auf die **erstellen** im Menü.  
  
 **Bereinigen Sie die Befehlszeile**  
 Gibt den Befehl ausgeführt werden, wenn sein **Bereinigen** geklickt wird, auf die **erstellen** Menü.  
  
 **Ausgabe**  
 Gibt den Namen der Datei, die die Ausgabe für die Befehlszeile enthalten soll. Der Dateiname basiert standardmäßig auf den Projektnamen.  
  
 **Präprozessor-Definitionen**  
 Gibt alle Präprozessordefinitionen sind, dass die Quelldateien verwenden. Der Standardwert richtet sich nach der aktuellen Plattform und Konfiguration.  
  
 **Suchpfad einschließen**  
 Gibt die Verzeichnisse, in denen der Compiler nach Includedateien durchsucht.  
  
 **Erzwungenes enthält**  
 Gibt Dateien an, denen der Präprozessor automatisch verarbeitet, auch wenn sie nicht in den Projektdateien enthalten sind.  
  
 **Assembly-Suchpfad**  
 Gibt die Verzeichnisse, in denen .NET Framework, wenn sucht, er versucht, die zum Auflösen von Assemblys für .NET.  
  
 **Erzwungene Verwendung von Assemblys**  
 Gibt die Assemblys, die .NET Framework automatisch verarbeitet.  
  
 **Zusätzliche Optionen**  
 Gibt alle zusätzlichen Compilerschalter für IntelliSense verwenden, wenn es sich um Dateien in C++ analysiert.  
  
 Informationen über den Zugriff auf die **NMake** auf der Seite finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
 Informationen zum programmgesteuerten Zugriff auf Member dieses Objekts finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCNMakeTool>.  
  
## <a name="see-also"></a>Siehe auch  
 [Eigenschaftenseiten](../ide/property-pages-visual-cpp.md)   
 [Vorgehensweise: Aktivieren von IntelliSense für Makefile-Projekte](../ide/how-to-enable-intellisense-for-makefile-projects.md)