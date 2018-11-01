---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: f8e5fbc50551b0a44b91787f99999301a8245069
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582466"
---
# <a name="library"></a>LIBRARY

Weist die Verknüpfung mit eine DLL zu erstellen. Zur gleichen Zeit erstellt der Verknüpfung eine Importbibliothek, es sei denn, eine .exp-Datei in den Build verwendet wird.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Hinweise

Die *Bibliothek* Argument gibt den Namen der DLL. Sie können auch die [/OUT](../../build/reference/out-output-file-name.md) Linkeroption, um die DLL Ausgabe-Namen angeben.

Der BASE =*Adresse* Argument legt die Basisadresse, die das Betriebssystem verwendet, um die DLL zu laden. Dieses Argument überschreibt den Standardspeicherort für die DLL der 0 x 10000000. Finden Sie in der Beschreibung der [/BASE](../../build/reference/base-base-address.md) Option Einzelheiten der Basisadressen.

Denken Sie daran, verwenden Sie die [/DLL](../../build/reference/dll-build-a-dll.md) bei der Erstellung einer DLL-Linkeroption.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](../../build/reference/rules-for-module-definition-statements.md)