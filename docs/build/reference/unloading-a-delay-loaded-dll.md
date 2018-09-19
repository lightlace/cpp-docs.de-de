---
title: Entladen einer verzögert geladenen DLL | Microsoft-Dokumentation
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
ms.openlocfilehash: fa7b9652c37b6c4e841a798dae3cfeb69779b5ff
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719926"
---
# <a name="unloading-a-delay-loaded-dll"></a>Entladen einer verzögert geladenen DLL

Die Hilfsfunktion für standardmäßig bereitgestellten verzögertes Laden überprüft, um festzustellen, ob die Deskriptoren für verzögertes Laden in das Feld Name einen Zeiger und eine Kopie der ursprünglichen Importadresstabelle (IAT) zu erhalten. Wenn dies der Fall ist, speichert es einen Zeiger in einer Liste auf den Import verzögert-Deskriptor. Dadurch wird die Hilfsfunktion zum Suchen von der DLL nach Namen an die DLL explizit entladen zu unterstützen.

Hier sind die zugehörigen Strukturen und Funktionen für Explizites Entladen einer verzögert geladenen DLL:

```cpp
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

Die-Implementierung für-Struktur wird implementiert, die Verwendung einer C++-Klasse, die verwendet **LocalAlloc** und **LocalFree** Implementierungen wie der Operator **neue** and -Operator  **Löschen Sie** bzw. Diese Optionen werden in einer standardmäßigen verknüpfte Liste, die mithilfe von __puiHead als der Anfang der Liste beibehalten.

Aufruf __FUnloadDelayLoadedDLL versucht, den Namen finden Sie in der Liste der geladenen DLLs (eine genaue Übereinstimmung erforderlich ist) bereitstellen. Wenn gefunden, die Kopie der IAT im Name kopiert wird oberhalb der ausgeführten IAT Thunk Zeiger wiederherstellen, wird die Bibliothek mit freigegeben **FreeLibrary**, den entsprechenden **-Implementierung für** Datensatz aus aufgehoben wird die Liste und gelöscht, und "true" zurückgegeben.

Das Argument von __FUnloadDelayLoadedDLL2 ist Groß-/Kleinschreibung beachtet. Beispielsweise würden Sie Folgendes angeben:

```cpp
__FUnloadDelayLoadedDLL2("user32.DLL");
```

und nicht:

```cpp
__FUnloadDelayLoadedDLL2("User32.DLL");.
```

## <a name="see-also"></a>Siehe auch

[Die Hilfsfunktion](understanding-the-helper-function.md)