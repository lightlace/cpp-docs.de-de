---
title: "Explizites Verkn&#252;pfen"
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
  - "Explizite Verknüpfung [C++]"
ms.assetid: 1e13d960-a195-4e6d-9864-7d8f3a701f4b
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Explizites Verkn&#252;pfen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei der expliziten Verknüpfung müssen Anwendungen einen Funktionsaufruf absetzen, um die DLL zur Laufzeit explizit zu laden.  Für die explizite Verknüpfung mit einer DLL muss eine Anwendung folgende Schritte ausführen:  
  
-   **LoadLibrary** \(oder eine ähnliche Funktion\) aufrufen, um die DLL zu laden und ein Modulhandle zu erhalten.  
  
-   **GetProcAddress** aufrufen, um einen Funktionszeiger auf jede exportierte Funktion zu erhalten, die durch die Anwendung aufgerufen wird.  Da Anwendungen die DLL\-Funktionen über einen Zeiger aufrufen, muss der Compiler keine externen Verweise generieren. Folglich ist es auch nicht erforderlich, eine Importbibliothek zu verknüpfen.  
  
-   **FreeLibrary** aufrufen, wenn die DLL nicht mehr benötigt wird.  
  
 Beispiel:  
  
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
  
## Was möchten Sie tun?  
  
-   [Implizite Verknüpfungen verwenden](../build/linking-implicitly.md)  
  
-   [Festlegen, welche Verknüpfungsmethode verwendet werden soll](../build/determining-which-linking-method-to-use.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   ["LoadLibrary" und "AfxLoadLibrary"](../build/loadlibrary-and-afxloadlibrary.md)  
  
-   [GetProcAddress](../build/getprocaddress.md)  
  
-   ["FreeLibrary" und "AfxFreeLibrary"](../build/freelibrary-and-afxfreelibrary.md)  
  
-   [Von Windows verwendeter Suchpfad zum Auffinden einer DLL](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## Siehe auch  
 [Verknüpfen einer ausführbaren Datei mit einer DLL](../build/linking-an-executable-to-a-dll.md)