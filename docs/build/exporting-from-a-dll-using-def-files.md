---
title: "Exportieren aus einer DLL mithilfe von DEF-Dateien | Microsoft Docs"
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
  - "DEF-Dateien [C++], Exportieren aus DLLs"
  - "DEF-Dateien [C++], Exportieren aus DLLs"
  - "Exportieren von DLLs [C++], DEF-Dateien"
ms.assetid: 9d31eda2-184e-47de-a2ee-a93ebd603f8e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Exportieren aus einer DLL mithilfe von DEF-Dateien
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine Moduldefinitionsdatei \(.def\) ist eine Textdatei mit einer oder mehreren Modulanweisungen, die verschiedene Attribute einer DLL beschreiben.  Wenn Sie für das Exportieren von DLL\-Funktionen nicht das **\_\_declspec\(dllexport\)**\-Schlüsselwort verwenden, ist eine DEF\-Datei für die DLL erforderlich.  
  
 Eine DEF\-Datei muss mindestens die folgenden Moduldefinitionsanweisungen enthalten:  
  
-   Die erste Anweisung in der Datei muss die **LIBRARY**\-Anweisung sein.  Sie kennzeichnet die Zugehörigkeit der DEF\-Datei zu einer DLL.  Auf die **LIBRARY**\-Anweisung folgt der Name der DLL.  Der Linker speichert diesen Namen in der Importbibliothek der DLL.  
  
-   Durch die **EXPORTS**\-Anweisung werden die Namen und optional die Ordinalwerte der von der DLL exportierten Funktionen aufgelistet.  Sie weisen der Funktion einen Ordinalwert zu, indem Sie dem Funktionsnamen ein @\-Zeichen und eine Zahl nachstellen.  Die Ordinalzahlen müssen sich in einem Bereich von 1 bis N befinden, wobei N die Gesamtzahl der von der DLL exportierten Funktionen angibt.  Informationen zum Exportieren von Funktionen anhand der Ordnungszahl finden Sie unter diesem Thema sowie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
 Die DEF\-Datei für eine DLL, die den Code für die Implementierung einer binären Suchstruktur enthält, könnte z. B. folgendermaßen aussehen:  
  
```  
LIBRARY   BTREE  
EXPORTS  
   Insert   @1  
   Delete   @2  
   Member   @3  
   Min   @4  
```  
  
 Wenn Sie zum Erstellen einer MFC\-DLL den [MFC\-DLL\-Assistenten](../mfc/reference/mfc-dll-wizard.md) verwenden, erstellt der Assistent eine DEF\-Gerüstdatei und fügt sie automatisch dem Projekt hinzu.  Fügen Sie die Namen der zu exportierenden Funktionen in diese Datei ein.  Für MFC\-fremde DLLs müssen Sie die DEF\-Datei selbst erstellen und sie dem Projekt hinzufügen.  
  
 Wenn Sie Funktionen in eine C\+\+\-Datei exportieren, müssen Sie entweder die ergänzten Namen in die DEF\-Datei einfügen oder die exportierten Funktionen unter Verwendung von extern "C" mit der standardmäßigen C\-Bindung definieren.  Wenn Sie die ergänzten Namen in der DEF\-Datei angeben müssen, können Sie diese mithilfe des Tools [DUMPBIN](../build/reference/dumpbin-reference.md) oder mit der [\/MAP](../build/reference/map-generate-mapfile.md)\-Linkeroption abrufen.  Beachten Sie, dass die vom Compiler erzeugten, ergänzten Namen compilerspezifisch sind.  Wenn Sie die vom Visual C\+\+\-Compiler erzeugten, ergänzten Namen in eine DEF\-Datei einfügen, ist es erforderlich, dass Anwendungen, die mit der DLL verknüpft werden, mit derselben Version von Visual C\+\+ erstellt wurden. Auf diese Weise ist gewährleistet, dass die ergänzten Namen in der aufrufenden Anwendung mit den exportierten Namen in der DEF\-Datei der DLL übereinstimmen.  
  
 Wenn Sie eine [Erweiterungs\-DLL](../build/extension-dlls-overview.md) erstellen und den Export über eine DEF\-Datei vornehmen, fügen Sie den folgenden Code am Anfang und am Ende der Headerdateien ein, in denen die exportierten Klassen enthalten sind:  
  
```  
#undef AFX_DATA  
#define AFX_DATA AFX_EXT_DATA  
// <body of your header file>  
#undef AFX_DATA  
#define AFX_DATA  
```  
  
 Diese Zeilen stellen sicher, dass MFC\-Variablen, die intern verwendet bzw. Klassen hinzugefügt werden, von der Erweiterungs\-DLL exportiert \(bzw. importiert\) werden.  Wenn Sie z. B. eine Klasse mithilfe von `DECLARE_DYNAMIC` ableiten, wird das Makro erweitert und Ihrer Klasse wird eine Membervariable `CRuntimeClass` hinzugefügt.  Ohne diese vier Zeilen wird die DLL u. U. nicht einwandfrei kompiliert bzw. verknüpft, oder es tritt ein Fehler auf, wenn die Clientanwendung mit der DLL verknüpft wird.  
  
 Der Linker verwendet beim Erstellen der DLL die DEF\-Datei, um eine Exportdatei \(.exp\) und eine Importbibliothek \(.lib\) zu erstellen.  Anschließend verwendet der Linker die Exportdatei zum Erstellen der DLL\-Datei.  Ausführbare, implizit mit der DLL verknüpfte Dateien werden bei ihrer Erstellung mit der Importbibliothek verknüpft.  
  
 Beachten Sie, dass MFC selbst die DEF\-Dateien verwendet, um Funktionen und Klassen aus MFCx0.dll zu exportieren.  
  
## Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von \_\_declspec\(dllexport\)](../build/exporting-from-a-dll-using-declspec-dllexport.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C\-Funktionen zur Verwendung in ausführbaren C\- oder C\+\+\-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [DEF\-Dateien](../build/reference/module-definition-dot-def-files.md)  
  
-   [Regeln für Moduldefinitionsanweisungen](../build/reference/rules-for-module-definition-statements.md)  
  
-   [Ergänzte Namen](../build/reference/decorated-names.md)  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)