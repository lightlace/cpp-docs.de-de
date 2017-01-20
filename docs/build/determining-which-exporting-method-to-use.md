---
title: "Bestimmen der geeigneten Exportmethode"
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
  - "DEF-Dateien [C++], Exportieren aus DLLs"
  - "__declspec(dllexport)-Schlüsselwort [C++]"
  - "DEF-Dateien [C++], Exportieren aus DLLs"
  - "Exportieren von DLLs [C++], Methodenvergleich"
ms.assetid: 66d773ed-935c-45c2-ad03-1a060874b34d
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Bestimmen der geeigneten Exportmethode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Sie können Funktionen in jedem der zwei Methoden\-ein .def oder des Schlüsselworts `__declspec(dllexport)` exportieren.  Zur Verbesserung zu entscheiden welche Methode für die DLL besser ist, sollten Sie folgende Fragen:  
  
-   Planen, mehr später Funktionen zu exportieren?  
  
-   Wird die DLL nur von Anwendungen, die neu erstellen können, oder wird die Verwendung von Anwendungen, dass Sie nicht REBUILD\-für Beispiel können, Anwendungen verwendet, die von Drittanbietern erstellt werden?  
  
## Vor\- und Nachteile der Verwendung von DEF\-Dateien  
 Das Exportieren von Funktionen in einer DEF\-Datei gibt Ihnen Kontrolle über den Exportordnungszahlen.  Wenn Sie eine exportierte Funktion der DLL hinzufügen, können Sie ihr einen höheren Wert als jede andere exportierte Funktion zuweisen.  Wenn Sie dies durchführen, müssen Anwendungen, die die implizite Verknüpfung verwenden, nicht mit der Importbibliothek erneut binden, die die neue Funktion.  Dies ist sehr praktisch, wenn Sie eine DLL für viele Anwendungen entwerfen, da Sie neue Funktionen hinzufügen und außerdem sicherstellen können, dass sie fortgesetzt wird, um mit Anwendungen ordnungsgemäß funktionieren, die bereits auf sie basieren.  Beispielsweise werden die MFC\-DLLs erstellt, indem die DEF\-Dateien verwendet.  
  
 Ein anderer Vorteil der Verwendung einer DEF\-Datei besteht darin, dass Sie das `NONAME`\-Attribut verwenden können, um eine Funktion zu exportieren.  Dadurch wird nur der Ordinalwert in der Exporttabelle der DLL ein.  Bei DLLs, die zahlreiche exportierte Funktionen haben, mithilfe des `NONAME`\-Attributs kann die Größe der DLL\-Datei reduzieren.  Informationen dazu, wie einer Moduldefinitionsanweisung, finden Sie unter [Regeln für Moduldefinitionsanweisungen](../build/reference/rules-for-module-definition-statements.md).  Informationen zum Ordnungsexport, finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
 Ein Nachteil bei Verwendung einer DEF\-Datei besteht darin, dass, wenn Sie Funktionen in eine C\+\+\-Datei exportieren, Sie entweder die ergänzten Namen in die DEF\-Datei einfügen oder die exportierten Funktionen definieren müssen, indem Sie extern "C" verwenden, um die Namensergänzung zu vermeiden, die vom Visual C\+\+\-Compiler vorgenommen wird.  
  
 Wenn Sie sich stellen, die ergänzten Namen in die DEF\-Datei, können Sie erhalten, indem Sie das Tool [DUMPBIN](../build/reference/dumpbin-reference.md) verwenden oder die [\/MAP](../build/reference/map-generate-mapfile.md) Linker Option verwenden.  Die ergänzten Namen, die vom Compiler erzeugten, compilerspezifisch sind; daher Sie die ergänzten Namen stellen, die vom Compiler in eine DEF\-Datei erzeugt wurden, müssen die Anwendungen, die mit der DLL verknüpft werden, auch erstellt werden, indem die gleiche Version des Compilers dass die ergänzten Namen in der aufrufenden Anwendungs\-Abgleichung die exportierten Namen in der DEF\-Datei der DLL verwendet.  
  
## Gründe für und gegen die Verwendung von "\_\_declspec\(dllexport\)"  
 Mit `__declspec(dllexport)` ist äußerst bequem, da weder eine DEF\-Datei bereitgestellt noch die ergänzten Namen exportierter Funktionen ermittelt werden müssen.  Allerdings wird die Nützlichkeit dieser Methode des Exportierens von der Anzahl verknüpfter Anwendungen begrenzt, dass Sie bereit sind neu zu erstellen.  Wenn Sie die DLL mit neuen Exporten neu erstellen, müssen die Anwendungen auch neu erstellen, da die ergänzten Namen für exportierte C\+\+\-Funktionen sich ändern können, wenn Sie eine andere Version des Compilers verwenden, um es neu zu erstellen.  
  
### Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C\-Funktionen zur Verwendung in ausführbaren C\- oder C\+\+\-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)