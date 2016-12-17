---
title: "Entladen einer verz&#246;gert geladenen DLL"
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
  - "__FUnloadDelayLoadedDLL2"
  - "Verzögertes Laden von DLLs, Entladen"
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Entladen einer verz&#246;gert geladenen DLL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Von der standardmäßig bereitgestellten Hilfsfunktion für verzögertes Laden wird überprüft, ob die Deskriptoren für verzögertes Laden im **pUnloadIAT**\-Feld einen Zeiger und eine Kopie der ursprünglichen Importadressentabelle \(IAT\) besitzen.  Falls ja, wird in einer Liste ein Zeiger auf den Deskriptor für verzögertes Importieren gespeichert.  Dadurch kann die DLL von der Hilfsfunktion über ihren Namen gefunden und das explizite Entladen dieser DLL unterstützt werden.  
  
 Nachstehend sind die verbundenen Strukturen und Funktionen aufgeführt, die zum expliziten Entladen einer verzögert geladenen DLL erforderlich sind:  
  
```  
//  
// Unload support from delayimp.h  
//  
  
// routine definition; takes a pointer to a name to unload  
  
ExternC  
BOOL WINAPI  
__FUnloadDelayLoadedDLL2(LPCSTR szDll);  
  
// structure definitions for the list of unload records  
typedef struct UnloadInfo * PUnloadInfo;  
typedef struct UnloadInfo {  
    PUnloadInfo     puiNext;  
    PCImgDelayDescr pidd;  
    } UnloadInfo;  
  
// from delayhlp.cpp  
// the default delay load helper places the unloadinfo records in the   
// list headed by the following pointer.  
ExternC  
PUnloadInfo __puiHead;  
```  
  
 Die **UnloadInfo**\-Struktur wird durch eine C\+\+\-Klasse implementiert, die eine **LocalAlloc**\-Implementierung für den Operator **new** und eine **LocalFree**\-Implementierung für den Operator **delete** verwendet.  Diese Optionen werden in einer standardmäßig verknüpften Liste mit dem **\_\_puiHead**\-Header verwaltet.  
  
 Beim Aufruf von **\_\_FUnloadDelayLoadedDLL** wird versucht, den angegeben Namen in der Liste der geladenen DLLs zu finden, wobei exakte Übereinstimmung erforderlich ist.  Wenn der Name gefunden wird, wird die IAT\-Kopie in **pUnloadIAT** an den Anfang der ausgeführten IAT kopiert, um die Thunkzeiger wiederherzustellen. Danach wird die Bibliothek mit **FreeLibrary** freigegeben, die Verknüpfung des entsprechenden **UnloadInfo**\-Datensatzes mit der Liste aufgehoben, der Datensatz gelöscht und **TRUE** zurückgegeben.  
  
 Vom Argument von **\_\_FUnloadDelayLoadedDLL2** wird Groß\- und Kleinschreibung beachtet.  Folgendes kann angegeben werden:  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 aber nicht:  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## Siehe auch  
 [Understanding the Helper Function](assetId:///6279c12c-d908-4967-b0b3-cabfc3e91d3d)