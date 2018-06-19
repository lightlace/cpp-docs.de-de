---
title: Anforderungen für STL/CLR-Containerelemente | Microsoft Docs
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
ms.openlocfilehash: 523b3e8d3f9c04a933f37032fcea670d75dafccf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33162435"
---
# <a name="requirements-for-stlclr-container-elements"></a>Anforderungen für STL/CLR-Containerelemente
Alle Verweistypen, die in STL/CLR-Container eingefügt werden müssen mindestens die folgenden Elemente umfassen:  
  
-   Öffentlichen Kopierkonstruktor.  
  
-   Eine öffentliche Zuweisungsoperator.  
  
-   Einen öffentlichen Destruktor.  
  
 Darüber hinaus assoziative Container wie z. B. [festgelegt](../dotnet/set-stl-clr.md) und [Zuordnung](../dotnet/map-stl-clr.md) benötigen einen öffentlich definierten Vergleichsoperator, also `operator<` standardmäßig. Einige Vorgänge in Containern möglicherweise auch einen öffentlichen Standardkonstruktor und einen öffentlichen Äquivalenzoperator definiert werden.  
  
 Wie Verweistypen, Werttypen und Handles zum Verweisen auf Typen, die in ein assoziativer Container eingefügt werden sollen benötigen einen Vergleichsoperator z. B. `operator<` definiert. Die Anforderungen für einen öffentlichen Kopierkonstruktor, öffentliche Zuweisungsoperator und einen öffentlichen Destruktor sind nicht für Werttypen oder Handles zum Verweisen auf Typen vorhanden.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Standardbibliotheksreferenz](../standard-library/cpp-standard-library-reference.md)