---
title: Speicherverwaltung mit CStringT | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bbf623344ec52abce28a08670e7f3cd09140563b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-with-cstringt"></a>Speicherverwaltung mit CStringT
Klasse [CStringT](../atl-mfc-shared/reference/cstringt-class.md) ist eine Vorlagenklasse, die zur Bearbeitung von Zeichenfolgen mit variabler Länge. Der Arbeitsspeicher für diese Zeichenfolgen enthalten reserviert und freigegeben, die über einen String-Manager-Objekt verknüpft sind, wobei jede Instanz von `CStringT`. MFC und ATL bieten standardmäßig Instanziierungen von `CStringT`namens `CString`, `CStringA`, und `CStringW`, das Bearbeiten von Zeichenfolgen, die von verschiedenen Zeichentypen. Diese Zeichentypen sind vom Typ **TCHAR**, `char`, und `wchar_t`zugeordnet. Diese Zeichenfolge Standardtypen verwenden Zeichenfolge, die aus den Prozessheap (in ATL) oder dem CRT-Heap (in MFC) Speicher belegt wird. In vielen Anwendungen reicht diese Speicherbelegungsschema. Verwenden Sie jedoch für Code, der rechenintensiven von Zeichenfolgen (oder Multithreadcode), die die Standard-Speicher-Manager nicht optimal ausgeführt werden können. In diesem Thema wird beschrieben, wie das Standardverhalten für die Verwaltung von Arbeitsspeicher von überschreiben `CStringT`, erstellen Zuweisungen speziell für die jeweilige Aufgabe optimiert.  
  
-   [Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (grundlegende Methode)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Vermeiden von Heapkonflikten](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Implementierung eines benutzerdefinierten Zeichenfolgenmanagers (fortgeschrittene Methode)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT: Ein Beispiel eines benutzerdefinierten Zeichenfolge-Managers](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>Siehe auch  
 [CustomString-Beispiel](../visual-cpp-samples.md)

