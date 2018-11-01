---
title: Anforderungen für STL/CLR-Containerelemente
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 0744d38a08dbd972b786e1cc74c112322ecf181f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428573"
---
# <a name="requirements-for-stlclr-container-elements"></a>Anforderungen für STL/CLR-Containerelemente

Alle Verweistypen zulässig, die STL/CLR-Container eingefügt werden, müssen mindestens die folgenden Elemente umfassen:

- Öffentlichen Kopierkonstruktor.

- Eine öffentliche Zuweisungsoperator.

- Einen öffentlichen Destruktor.

Darüber hinaus assoziative Container wie z. B. [festgelegt](../dotnet/set-stl-clr.md) und [Zuordnung](../dotnet/map-stl-clr.md) müssen einen öffentlich definierten Vergleichsoperator, handelt es sich `operator<` standardmäßig. Einige Vorgänge in Containern erfordern möglicherweise auch einen öffentlichen Standardkonstruktor und einen öffentlichen Äquivalenzoperator definiert werden.

Wie Verweistypen, Werttypen und Handles zum Verweisen auf Typen, die in einen assoziativen Container eingefügt werden sollen benötigen einen Vergleichsoperator z. B. `operator<` definiert. Die Anforderungen für die öffentlichen Kopierkonstruktor und Zuweisungsoperator öffentliche einen öffentlichen Destruktor sind nicht für Werttypen und Handles Verweistypen vorhanden.

## <a name="see-also"></a>Siehe auch

[C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)