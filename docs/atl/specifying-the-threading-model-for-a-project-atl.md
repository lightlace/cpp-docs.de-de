---
title: Angeben des Threadingmodells für ein Projekt (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- _ATL_FREE_THREADED macro
- _ATL_APARTMENT_THREADED macro
- ATL, multithreading
- threading [ATL], models
- _ATL_SINGLE_THREADED macro
ms.assetid: 6b571078-521c-4f3e-9f08-482aa235a822
ms.openlocfilehash: 69c1c80bba0b09ce69e0b9b9b27296ef2508e60b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62275216"
---
# <a name="specifying-the-threading-model-for-a-project-atl"></a>Angeben des Threadingmodells für ein Projekt (ATL)

Die folgenden Makros sind verfügbar, geben Sie das Threadingmodell eines ATL-Projekts:

|Makro|Richtlinien für die Verwendung|
|-----------|--------------------------|
|_ATL_SINGLE_THREADED|Wenn alle Ihre Objekte verwenden Sie die einzelne threading-Modell definieren.|
|_ATL_APARTMENT_THREADED|Definieren Sie, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen verwenden.|
|_ATL_FREE_THREADED|Wenn eine oder mehrere der Objekte frei oder neutrale threading verwenden, definieren. Vorhandener Code enthält Verweise auf das entsprechende Makro [_ATL_MULTI_THREADED](reference/compiler-options-macros.md#_atl_multi_threaded).|

Wenn Sie diese Makros nicht für Ihr Projekt definieren, werden die _ATL_FREE_THREADED in Kraft.

Die Makros, die sich auf die Leistung zur Laufzeit folgendermaßen auswirken:

- Das Makro, das die Objekte in Ihrem Projekt entspricht, angeben kann laufzeitleistung verbessern.

- Angeben einer höheren Ebene des Makros, z. B. Wenn Sie _ATL_APARTMENT_THREADED angeben, wenn alle Ihre Objekte einzelne sind Singlethread ist, wird Leistung zur Laufzeit leicht beeinträchtigt werden.

- Makros, z. B. eine niedrigere Ebene angibt, ob es sich bei Angabe _ATL_SINGLE_THREADED, wenn eine oder mehrere der Objekte Apartmentthreading für Anwendungen bzw. freies threading, kann die Anwendung zur Laufzeit fehlschlagen.

Finden Sie unter [Optionen, ATL-Assistent für einfache Objekte](../atl/reference/options-atl-simple-object-wizard.md) eine Beschreibung der threading-Modellen für ein ATL-Objekt verfügbar.

## <a name="see-also"></a>Siehe auch

[Konzepte](../atl/active-template-library-atl-concepts.md)
