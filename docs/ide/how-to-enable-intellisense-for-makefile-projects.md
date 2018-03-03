---
title: "Vorgehensweise: Aktivieren von IntelliSense für Makefile-Projekte | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCNMakeTool.IntelliSense
dev_langs:
- C++
helpviewer_keywords:
- Makefile projects, IntelliSense
- IntelliSense, Makefile projects
ms.assetid: 9443f453-f18f-4f12-a9a1-ef9dbf8b188f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fae3ec35259250f71ad672d9468b991033608ae4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-enable-intellisense-for-makefile-projects"></a>Gewusst wie: Aktivieren von IntelliSense für Makefile-Projekte
IntelliSense kann nicht in der IDE für Visual C++-Makefile-Projekte funktionieren, wenn Sie bestimmte Einstellungen oder der Compileroptionen, Projekt werden nicht ordnungsgemäß eingerichtet. Verwenden Sie dieses Verfahren zum Konfigurieren von Visual C++-Makefile-Projekte, so, dass IntelliSense funktioniert, wenn Makefile-Projekte in der Entwicklungsumgebung von Visual Studio geöffnet sind.  
  
### <a name="to-enable-intellisense-for-makefile-projects-in-the-ide"></a>So aktivieren Sie IntelliSense für Makefile-Projekte in der IDE  
  
1.  Öffnen der **Eigenschaftenseiten** (Dialogfeld). Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Wählen Sie die **NMake** Eigenschaft Seite, und ändern Sie Eigenschaften unter **IntelliSense** je nach Bedarf.  
  
    -   Legen Sie die **Präprozessordefinitionen** Eigenschaft Präprozessorsymbolen im Makefile-Projekt definieren. Finden Sie unter [/d (Präprozessordefinitionen)](../build/reference/d-preprocessor-definitions.md), Weitere Informationen.  
  
    -   Legen Sie die **Suchpfad einschließen** Eigenschaft, um die Liste der Verzeichnisse angeben, die der Compiler durchsucht, um Dateiverweise aufzulösen, die Präprozessordirektiven im Makefile-Projekt übergeben werden. Finden Sie unter [/i (Zusätzliche Includeverzeichnisse)](../build/reference/i-additional-include-directories.md), Weitere Informationen.  
  
         Für Projekte, die mit CL erstellt werden. Legen Sie die EXE-Datei in einem Befehlsfenster die **INCLUDE** Umgebungsvariable Verzeichnisse angeben, die der Compiler durchsucht, um Dateiverweise aufzulösen, die Präprozessordirektiven im Makefile-Projekt übergeben werden.  
  
    -   Legen Sie die **erzwungene Includes** Eigenschaft, um anzugeben, welcher Prozess Headerdateien beim Erstellen des Makefile-Projekts. Finden Sie unter [/Fi (Name Forced Include-Datei)](../build/reference/fi-name-forced-include-file.md), Weitere Informationen.  
  
    -   Legen Sie die **Assemblysuchpfad** Eigenschaft, um die Liste der Verzeichnisse angeben, die der Compiler durchsucht, um Verweise auf Assemblys von .NET in Ihrem Projekt zu beheben. Finden Sie unter [/AI (Metadatenverzeichnisse festlegen)](../build/reference/ai-specify-metadata-directories.md), Weitere Informationen.  
  
    -   Legen Sie die **erzwungene Verwendung von Assemblys** Eigenschaft an, welche .NET Assemblys zu verarbeiten, wenn Sie die Makefile-Projekt zu erstellen. Finden Sie unter [/FU (Name Forced #using-Datei)](../build/reference/fu-name-forced-hash-using-file.md), Weitere Informationen.  
  
    -   Legen Sie die **Zusatzoptionen** Eigenschaft, um zusätzliche Compilerschalter, die von Intellisense verwendet werden, beim Analysieren von C++-Dateien anzugeben.  
  
4.  Klicken Sie auf **OK** um die Eigenschaftenseiten zu schließen.  
  
5.  Verwenden der **alle speichern** Befehl aus, um die Einstellungen für die geänderte Projekt speichern.  
  
 Das nächste Mal öffnen Sie die Makefile-Projekt, in der Visual Studio-Entwicklungsumgebung, führen Sie die **Projektmappe bereinigen** Befehl und klicken Sie dann die **Projektmappe** Befehl Makefile-Projekt. IntelliSense sollte in der IDE ordnungsgemäß funktionieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense)   
 [NMAKE-Referenz](../build/nmake-reference.md)   
 [Vorgehensweise: Erstellen eines C++-Projekts aus vorhandenem Code](../ide/how-to-create-a-cpp-project-from-existing-code.md)