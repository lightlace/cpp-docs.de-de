---
title: Anforderungen für STL/CLR-Containerelemente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: fcba36fdf280cef31efb9a84288475fcbb82b291
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400420"
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