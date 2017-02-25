---
title: "GetProcAddress | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetProcAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], GetProcAddress"
  - "GetProcAddress-Methode"
  - "Ordnungszahlenexporte [C++]"
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# GetProcAddress
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prozesse, die explizit mit einer DLL verknüpft werden, rufen [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) auf, um die Adresse einer exportierten Funktion in der DLL zu erhalten.  Sie rufen die DLL\-Funktion dann über den zurückgegebenen Funktionszeiger auf.  **GetProcAddress** verwendet als Parameter das \(von **LoadLibrary**, `AfxLoadLibrary` oder **GetModuleHandle** zurückgegebene\) DLL\-Modulhandle sowie entweder den Namen der Funktion, die Sie aufrufen möchten, oder ihre Exportordinalzahl.  
  
 Da Sie die DLL\-Funktion über einen Zeiger aufrufen und zur Kompilierungszeit keine Typüberprüfung erfolgt, sollten Sie sicherstellen, dass die Parameter für die Funktion korrekt sind, damit Sie nicht den auf dem Stapel belegten Speicherbereich überschreiten und eine Zugriffsverletzung verursachen.  Eine Möglichkeit die Typsicherheit zu gewährleisten besteht darin, sich die Funktionsprototypen der exportierten Funktionen anzusehen und entsprechende Typdefinitionen für die Funktionszeiger zu erstellen.  Beispiel:  
  
```  
typedef UINT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT);  
...  
  
HINSTANCE hDLL;               // Handle to DLL  
LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
DWORD dwParam1;  
UINT  uParam2, uReturnVal;  
  
hDLL = LoadLibrary("MyDLL");  
if (hDLL != NULL)  
{  
   lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL,  
                                           "DLLFunc1");  
   if (!lpfnDllFunc1)  
   {  
      // handle the error  
      FreeLibrary(hDLL);  
      return SOME_ERROR_CODE;  
   }  
   else  
   {  
      // call the function  
      uReturnVal = lpfnDllFunc1(dwParam1, uParam2);  
   }  
}  
```  
  
 Wie Sie die gewünschte Funktion beim Aufrufen von **GetProcAddress** angeben, hängt davon ab, wie die DLL erstellt wurde.  
  
 Sie können die Exportordinalzahl nur ermitteln, wenn die zu verknüpfende DLL mithilfe einer Moduldefinitionsdatei \(.def\) erstellt wurde und die Ordinalzahlen zusammen mit den Funktionen im **EXPORTS**\-Abschnitt der DEF\-Datei für die DLL aufgeführt sind.  Wenn die DLL zahlreiche exportierte Funktionen aufweist, ist der Aufruf von **GetProcAddress** mit einer Exportordinalzahl geringfügig schneller als die Verwendung des Funktionsnamens, da die Exportordinalzahlen als Indizes für die Exporttabelle der DLL dienen.  Mit einer Exportordinalzahl kann die Funktion von **GetProcAddress** direkt ermittelt werden, und der angegebene Namen muss nicht mit den Funktionsnamen in der Exporttabelle der DLL verglichen werden.  Sie sollten jedoch **GetProcAddress** nur dann mit einer Exportordinalzahl aufrufen, wenn Sie die Zuordnung der Ordinalzahlen zu den exportierten Funktionen in der DEF\-Datei steuern können.  
  
## Was möchten Sie tun?  
  
-   [Implizite Verknüpfungen verwenden](../build/linking-implicitly.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   ["LoadLibrary" und "AfxLoadLibrary"](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [\<caps:sentence id\="tgt17" sentenceid\="8c920606bb67e2587dd3c3e5cf977593" class\="tgtSentence"\>FreeLibrary\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [Exportieren aus einer DLL mithilfe von DEF\-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
## Siehe auch  
 [DLLs in Visual C\+\+](../build/dlls-in-visual-cpp.md)