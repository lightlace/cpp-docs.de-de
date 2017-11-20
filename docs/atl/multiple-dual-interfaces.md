---
title: Mehrere duale Schnittstellen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 426109958cf9b34829c23ac0bfd59743f1681e72
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="multiple-dual-interfaces"></a>Mehrere duale Schnittstellen
Möglicherweise möchten Sie die Vorteile, die eine duale Schnittstelle (d. h. die Flexibilität der Vtable und späte Bindung, daher und die Klasse für Skriptsprachen als auch für C++ zur Verfügung) kombinieren mit den Techniken der mehrfachvererbung.  
  
 Obwohl es möglich, mehrere duale Schnittstellen für eine einzelnes COM-Objekt verfügbar zu machen, wird nicht empfohlen. Wenn mehrere duale Schnittstellen sind, es muss nur eine `IDispatch` Schnittstelle verfügbar gemacht werden. Die Techniken zur Verfügung, um sicherzustellen, dass dies der Fall ist tragen dies z. B. geringere-Funktion oder höhere Codekomplexität. Der Entwickler, die Berücksichtigung dieser Ansatz sollten sorgfältig abwägen, die vor- und Nachteile.  
  
## <a name="exposing-a-single-idispatch-interface"></a>Verfügbarmachen von einer einzelnen IDispatch-Schnittstelle  
 Es ist möglich, mehrere duale Schnittstellen für ein einzelnes Objekt verfügbar zu machen, durch Ableiten von zwei oder mehr spezialisierungen `IDispatchImpl`. Jedoch wenn Sie zulassen, Clients dass bei der Abfrage der `IDispatch` -Schnittstelle, müssen Sie verwenden die [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) Makro (oder [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) an die Basisklasse für die Verwendung der Implementierung von `IDispatch`.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]  
  
 Da nur ein `IDispatch` Schnittstelle verfügbar gemacht wird, Clients, die nur Zugriff auf Ihre Objekte über können die `IDispatch` Schnittstelle wird nicht in der Lage, auf die Methoden oder Eigenschaften in einer beliebigen anderen Schnittstelle zuzugreifen.  
  
## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Kombinieren von mehreren duale Schnittstellen in eine einzelne Implementierung von IDispatch  
 ATL bietet keine Unterstützung für das Kombinieren mehrerer dualer Schnittstellen in eine einzelne Implementierung von `IDispatch`. Es gibt jedoch mehrere Methoden für die manuell kombiniert die Schnittstellen, z. B. das Erstellen einer auf Vorlagen basierenden Klasse enthält eine Kombination der separaten `IDispatch` Schnittstellen, erstellen ein neues Objekt zum Ausführen der `QueryInterface` -Funktion oder über eine TypeInfo-basierte Implementierung eines geschachtelten Objekte zum Erstellen der `IDispatch` Schnittstelle.  
  
 Diese Ansätze haben Probleme mit potenziellen Namespacekonflikte, als auch Codekomplexität und verwaltbarkeit. Es wird nicht empfohlen, mehrere duale Schnittstellen zu erstellen.  
  
## <a name="see-also"></a>Siehe auch  
 [Duale Schnittstellen und ATL](../atl/dual-interfaces-and-atl.md)

