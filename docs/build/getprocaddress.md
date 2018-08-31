---
title: GetProcAddress | Microsoft-Dokumentation
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
ms.openlocfilehash: 91fd6b983d648b682cbd60fa6126189e102b9f1c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194358"
---
# <a name="getprocaddress"></a>GetProcAddress
Prozesse, die explizit Verknüpfen mit einer DLL-Aufrufs [GetProcAddress](https://msdn.microsoft.com/library/windows/desktop/ms683212) zum Abrufen der Adresse einer exportierten Funktion in der DLL. Sie rufen die DLL-Funktion dann über den zurückgegebenen Funktionszeiger auf. **GetProcAddress** nimmt als Parameter das DLL-Modulhandle (entweder vom **LoadLibrary**, `AfxLoadLibrary`, oder **GetModuleHandle**), und Sie gelangen Sie entweder den Namen der gewünschten-Funktion zum Aufruf oder die Ordnungszahl für einen Export der Funktion.  
  
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
  
 Wie Sie die Funktion sollen angeben, wenn der Aufruf von **GetProcAddress** abhängig, wie die DLL erstellt wurde.  
  
 Sie können die Exportordinalzahl nur ermitteln, wenn die DLL, die Sie zum Verknüpfen mit einer Moduldefinitionsdatei (.def) erstellt wurde und die Ordinalzahlen zusammen mit den Funktionen im aufgeführt sind die **EXPORTE** Abschnitt der DEF-Datei der DLL. Aufrufen von **GetProcAddress** Exportordinalzahl und hat den Namen der Funktion, mit einem Export ist etwas schneller, wenn die DLL zahlreiche exportierte Funktionen aufweist, da die Exportordinalzahlen dienen, wie die Tabelle Indizes in der DLLs zu exportieren. Mit einer Exportordinalzahl **GetProcAddress** Exportordinalzahl kann die Funktion direkt und nicht den angegebenen Namen auf den Funktionsnamen in der Exporttabelle der DLL verglichen. Sie sollten jedoch aufrufen **GetProcAddress** mit einer Exportordinalzahl nur dann, wenn Sie die Kontrolle über die Zuordnung der Ordinalzahlen zu den exportierten Funktionen in der DEF-Datei haben.  
  
## <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?  
  
-   [Implizit mit einer DLL verknüpfen](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [Bestimmen Sie welche Verknüpfungsmethode verwendet werden](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [LoadLibrary und AfxLoadLibrary](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [FreeLibrary](https://msdn.microsoft.com/library/windows/desktop/ms683152)  
  
-   [Exportieren aus einer DLL mithilfe von DEF-Dateien](../build/exporting-from-a-dll-using-def-files.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)