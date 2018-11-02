---
title: Entladen einer verzögert geladenen DLL
ms.date: 11/04/2016
helpviewer_keywords:
- __FUnloadDelayLoadedDLL2
- delayed loading of DLLs, unloading
ms.assetid: 6463bc71-020e-4aff-a4ca-90360411c54e
ms.openlocfilehash: ac23a82282215e70a6895e021d25437bc8890c6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460644"
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