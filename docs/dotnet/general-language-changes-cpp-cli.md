---
title: Allgemeine Sprachänderungen (C + c++ / CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: aede6cc0d4bd8e50d8662f301ffdfb7b6179a230
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33109137"
---
# <a name="general-language-changes-ccli"></a>Allgemeine Sprachänderungen (C++/CLI)
Eine Anzahl von CLR-Sprachfunktionen, die von Managed Extensions for C++ auf Visual C++ geändert.  
  
 Die Änderungen, die in diesem Abschnitt beschriebenen sind eine Art von Language – Vermischtes. Es beinhaltet eine Änderung bei der Behandlung von Zeichenfolgenliteralen, eine Änderung an der die überladungsauflösung zwischen einem Auslassungszeichen und das `Param` -Attributs sind die Änderung des `typeof` zu `typeid`, eine Änderung in der aufrufenden von Initialisiererlisten Konstruktor, und die eine neue Umwandlungsnotation Einführung der `safe_cast`.  
  
 [Zeichenfolgenliteral](../dotnet/string-literal.md)  
 Erläutert, wie die Behandlung von Zeichenfolgenliteralen geändert hat.  
  
 [Parameterarray und Ellipse](../dotnet/param-array-and-ellipsis.md)  
 Erläutert, wie `ParamArray` ist jetzt Vorrang vor den drei Punkten (`...`) zum Auflösen von Funktionsaufrufen mit einer unterschiedlichen Anzahl von Argumenten.  
  
 [typeof wird zu T::typeid](../dotnet/typeof-goes-to-t-typeid.md)  
 Erläutert, wie die `typeof` -Operator wurde ersetzt wurde, indem Sie `typeid`.  
  
 [Initialisiererlisten](../dotnet/initializer-lists.md)  
 Werden Änderungen in der aufrufenden Reihenfolge von Initialisiererlisten erläutert.  
  
 [Umwandlungsnotation und Einführung in safe_cast<>](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)  
 Erläutert Änderungen an Umwandlungsnotation und insbesondere die Einführung von `safe_cast`.  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in die C++/CLI-Migration](../dotnet/cpp-cli-migration-primer.md)