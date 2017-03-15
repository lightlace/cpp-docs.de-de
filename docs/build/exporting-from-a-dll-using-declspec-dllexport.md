---
title: "Exportieren aus einer DLL mithilfe von &quot;__declspec(dllexport)&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dllexport"
  - "__declspec"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllexport)-Schlüsselwort [C++]"
  - "Exportdirektiven [C++]"
  - "Exportieren von DLLs [C++], __declspec(dllexport)-Schlüsselwort"
  - "Namen [C++], DLL-Exporte nach"
ms.assetid: a35e25e8-7263-4a04-bad4-00b284458679
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Exportieren aus einer DLL mithilfe von &quot;__declspec(dllexport)&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\_\_export** wurde von Microsoft mit der 16\-Bit\-Compilerversion von Visual C\+\+ eingeführt, damit der Compiler die Exportnamen automatisch generieren und in einer LIB\-Datei speichern kann.  Diese LIB\-Datei kann dann wie eine statische LIB\-Datei zur Verknüpfung mit einer DLL verwendet werden.  
  
 In neueren Compilerversionen können Sie Daten, Funktionen, Klassen oder Memberfunktionen von Klassen aus einer DLL exportieren, indem Sie das **\_\_declspec\(dllexport\)**\-Schlüsselwort verwenden.  Mithilfe von **\_\_declspec\(dllexport\)** wird der Objektdatei die Exportdirektive hinzugefügt, sodass keine DEF\-Datei erforderlich ist.  
  
 Am deutlichsten zeigt sich diese einfache Handhabung beim Exportieren von ergänzten C\+\+\-Funktionsnamen.  Da es keine Standardspezifikation für die Namensergänzung gibt, kann der Name einer exportierten Funktion zwischen den einzelnen Compilerversionen variieren.  Bei Verwendung von **\_\_declspec\(dllexport\)** ist die Neukompilierung der DLL und der von ihr abhängigen EXE\-Dateien nur erforderlich, wenn Änderungen bei den Namenskonventionen auftreten.  
  
 Viele Exportdirektiven, z. B. Ordinalzahlen, NONAME und PRIVATE, können nur in einer DEF\-Datei angegeben werden, und es gibt keine Möglichkeit, diese Attribute ohne DEF\-Datei festzulegen.  Die Verwendung von **\_\_declspec\(dllexport\)** zusätzlich zu einer DEF\-Datei verursacht jedoch keine Erstellungsfehler.  
  
 Zum Exportieren von Funktionen muss das **\_\_declspec\(dllexport\)**\-Schlüsselwort links neben dem Schlüsselwort für die Aufrufkonvention stehen, sofern ein Schlüsselwort angegeben wird.  Beispiel:  
  
```  
__declspec(dllexport) void __cdecl Function1(void);  
```  
  
 Um alle öffentlichen Datenmember und Memberfunktionen einer Klasse zu exportieren, muss das Schlüsselwort, wie im nachfolgenden Beispiel dargestellt, links vom Klassennamen erscheinen:  
  
```  
class __declspec(dllexport) CExampleExport : public CObject  
{ ... class definition ... };  
```  
  
> [!NOTE]
>  `__declspec(dllexport)` kann nicht mit der `__clrcall`\-Aufrufkonvention für eine Funktion übernommen werden.  
  
 Beim Erstellen der DLL erstellen Sie in der Regel eine Headerdatei mit den Funktionsprototypen oder den zu exportierenden Klassen und fügen den Deklarationen in der Headerdatei anschließend **\_\_declspec\(dllexport\)** hinzu.  Um den Code lesbarer zu gestalten, definieren Sie ein Makro für **\_\_declspec\(dllexport\)** und verwenden anschließend das Makro für jedes Symbol, das Sie exportieren:  
  
```  
#define DllExport   __declspec( dllexport )   
```  
  
 **\_\_declspec\(dllexport\)** speichert Funktionsnamen in der Exporttabelle der DLL.  Informationen dazu, wie Sie die Größe der Tabelle verringern, finden Sie unter [Exportieren von Funktionen aus einer DLL über die Ordnungszahl statt über den Namen](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md).  
  
> [!NOTE]
>  Wenn Sie DLL\-Quellcode von Win16 auf Win32 portieren, ersetzen Sie jede Instanz von **\_\_export** durch **\_\_declspec\(dllexport\)**.  
  
 Zu Referenzzwecken können Sie die Win32\-Headerdatei Winbase.h durchsuchen.  Sie enthält Verwendungsbeispiele für **\_\_declspec\(dllimport\)**.  
  
## Was möchten Sie tun?  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
-   [Exportieren und Importieren mithilfe von AFX\_EXT\_CLASS](../build/exporting-and-importing-using-afx-ext-class.md)  
  
-   [Exportieren von C\+\+\-Funktionen zur Verwendung in ausführbaren C\-Dateien](../build/exporting-cpp-functions-for-use-in-c-language-executables.md)  
  
-   [Exportieren von C\-Funktionen zur Verwendung in ausführbaren C\- oder C\+\+\-Dateien](../build/exporting-c-functions-for-use-in-c-or-cpp-language-executables.md)  
  
-   [Ermitteln, welche Exportmethode verwendet werden soll](../build/determining-which-exporting-method-to-use.md)  
  
-   [Importieren in eine Anwendung mithilfe von \_\_declspec\(dllimport\)](../build/importing-into-an-application-using-declspec-dllimport.md)  
  
-   [Initialisieren einer DLL](../build/initializing-a-dll.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Das \_\_declspec\-Schlüsselwort](../cpp/declspec.md)  
  
-   [Importieren und Exportieren von Inlinefunktionen](../build/importing-and-exporting-inline-functions.md)  
  
-   [Gegenseitige Importe](../build/mutual-imports.md)  
  
## Siehe auch  
 [Exportieren aus einer DLL](../build/exporting-from-a-dll.md)