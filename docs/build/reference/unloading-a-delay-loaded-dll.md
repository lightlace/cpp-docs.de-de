---
title: Entladen einer verzögert geladenen DLL | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 724ee2ac3987c855f5e2102dee35d12785726641
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="unloading-a-delay-loaded-dll"></a>Entladen einer verzögert geladenen DLL
Das Hilfsobjekt standardmäßig bereitgestellten verzögerte Laden überprüft, ob die Deskriptoren für verzögertes Laden ein Zeiger und eine Kopie der ursprünglichen Importadresstabelle (IAT) im Feld "Name" aufweisen. Wenn dies der Fall ist, speichert es einen Zeiger in einer Liste auf den Import Verzögerungsdeskriptor. Dadurch wird die Hilfsfunktion, die anhand des Namens zur Unterstützung dieser DLL explizit Entladen der DLL zu suchen.  
  
 Hier werden die zugehörigen Strukturen und Funktionen für Explizites Entladen einer verzögert geladenen DLL:  
  
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
  
 Die-Implementierung-Struktur wird mithilfe von einem C++-Klasse, die verwendet implementiert **LocalAlloc** und **LocalAlloc** Implementierungen als seinen Operator **neue** and -Operator  **Löschen Sie** bzw. Diese Optionen werden in einer standardmäßigen verknüpfte Liste, die mithilfe von __puiHead als den Anfang der Liste beibehalten.  
  
 Aufrufen von __FUnloadDelayLoadedDLL versucht, den Namen zu finden Sie in der Liste der geladenen DLLs (eine genaue Übereinstimmung erforderlich ist) bereitstellen. Wenn gefunden, die Kopie der IAT in Name kopiert wird über den oberen Rand ausgeführten IAT Thunk Zeiger wiederhergestellt werden soll, wird die Bibliothek mit freigegeben **FreeLibrary**, den entsprechenden **-Implementierung** Datensatz aus aufgehoben wird die Liste gelöscht und "true" zurückgegeben.  
  
 Das Argument von __FUnloadDelayLoadedDLL2 wird Groß-/Kleinschreibung beachtet. Beispielsweise würden Sie Folgendes angeben:  
  
```  
__FUnloadDelayLoadedDLL2("user32.DLL");  
```  
  
 und nicht:  
  
```  
__FUnloadDelayLoadedDLL2("User32.DLL");.  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Die Hilfsfunktion](understanding-the-helper-function.md)