---
title: GetProcAddress | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
f1_keywords:
- GetProcAddress
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], GetProcAddress
- ordinal exports [C++]
- GetProcAddress method
ms.assetid: 48d14ae0-47ea-4c5d-96b1-2c158f1a26af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cec73a7d7aa212c6f53bc2654db6fe40ff96472a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="getprocaddress"></a>GetProcAddress
Prozesse, die explizit auf einen Anruf DLL verknüpfen [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212) zum Abrufen der Adresse einer exportierten Funktion in der DLL. Sie rufen die DLL-Funktion dann über den zurückgegebenen Funktionszeiger auf. **GetProcAddress** als Parameter akzeptiert, die DLL-Modulhandle (entweder zurückgegebenes **LoadLibrary**, `AfxLoadLibrary`, oder **GetModuleHandle**) und entweder den Namen der gewünschten Funktion akzeptiert zum Aufruf oder die Funktion Exportordinalzahl.  
  
 Da Sie die DLL-Funktion über einen Zeiger aufrufen und zur Kompilierzeit keine Typüberprüfung erfolgt, sollten Sie sicherstellen, dass die Parameter für die Funktion korrekt sind, damit Sie nicht den auf dem Stapel belegten Speicherbereich überschreiten und eine Zugriffsverletzung verursachen. Eine Möglichkeit die Typsicherheit zu gewährleisten besteht darin, sich die Funktionsprototypen der exportierten Funktionen anzusehen und entsprechende Typdefinitionen für die Funktionszeiger zu erstellen. Zum Beispiel:  
  
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
  
 Wie Sie die Funktion angeben beim Aufrufen von soll **GetProcAddress** abhängig, wie die DLL erstellt wurde.  
  
 Sie können die Exportordinalzahl nur abrufen, wenn die DLL, die zum Verknüpfen mit einer Moduldefinitionsdatei (.def) erstellt wird und die Ordinalzahlen zusammen mit den Funktionen im aufgeführt sind die **EXPORTE** Abschnitt der DEF-Datei für die DLL. Aufrufen von **GetProcAddress** Exportordinalzahl den Funktionsnamen mit einem Export wird etwas schneller, wenn die DLL zahlreiche exportierte Funktionen aufweist, da die Exportordinalzahlen als Indizes der DLL Exporttabelle dienen. Mit einer Exportordinalzahl **GetProcAddress** können, suchen Sie die Funktion direkt statt des angegebenen Namens als dem Funktionsnamen in der Exporttabelle der DLL zu vergleichen. Sie sollten jedoch aufrufen **GetProcAddress** mit einer Exportordinalzahl nur, wenn Sie die Kontrolle über die Zuordnung der Ordinalzahlen zu den exportierten Funktionen in der DEF-Datei haben.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Gewusst wie: implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Welche Verknüpfungsmethode ermitteln](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](http://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [Exportieren aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)