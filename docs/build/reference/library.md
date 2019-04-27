---
title: LIBRARY
ms.date: 11/04/2016
f1_keywords:
- LIBRARY
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
ms.openlocfilehash: b43f269726e8925abeefd41aab0edfd57b071035
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291092"
---
# <a name="library"></a>LIBRARY

Weist die Verknüpfung mit eine DLL zu erstellen. Zur gleichen Zeit erstellt der Verknüpfung eine Importbibliothek, es sei denn, eine .exp-Datei in den Build verwendet wird.

```
LIBRARY [library][BASE=address]
```

## <a name="remarks"></a>Hinweise

Die *Bibliothek* Argument gibt den Namen der DLL. Sie können auch die [/OUT](out-output-file-name.md) Linkeroption, um die DLL Ausgabe-Namen angeben.

Der BASE =*Adresse* Argument legt die Basisadresse, die das Betriebssystem verwendet, um die DLL zu laden. Dieses Argument überschreibt den Standardspeicherort für die DLL der 0 x 10000000. Finden Sie in der Beschreibung der [/BASE](base-base-address.md) Option Einzelheiten der Basisadressen.

Denken Sie daran, verwenden Sie die [/DLL](dll-build-a-dll.md) bei der Erstellung einer DLL-Linkeroption.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](rules-for-module-definition-statements.md)
