---
title: BIBLIOTHEK | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- LIBRARY
dev_langs:
- C++
helpviewer_keywords:
- LIBRARY .def file statement
ms.assetid: 1d7ccc92-e088-4ef7-9ef0-25c3862cc051
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43b14e8e8ff4871ba4319c7f4fac5545e72e710b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723553"
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