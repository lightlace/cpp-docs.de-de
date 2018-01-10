---
title: "Anforderungen für STL/CLR-Containerelemente | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 3317e3c9349963fc24b37b421def05c475732fd8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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