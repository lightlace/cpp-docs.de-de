---
title: Verwaltete Typen (C++-CL) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9e7bbd9687c3cc696b35e0284d55a18f59c898cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="managed-types-ccl"></a>Verwaltete Typen (C++/CL)
Die Syntax für die Deklaration von verwalteten Typen und die Erstellung und Verwendung von Objekten dieser Typen wurde erheblich von Managed Extensions für C++ in Visual C++ geändert wurde. Dies erfolgte, um deren Integration in das ISO C++-Typsystem zu erzielen. Diese Änderungen werden in den folgenden Abschnitten ausführlich dargestellt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)  
 Erläutert, wie ein verwaltetes deklarieren `class`, `struct`, oder `interface`.  
  
 [Deklaration eines CLR-Verweisklassenobjekts](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 Erläutert, wie ein Typ Referenzklassenobjekt verwenden ein Trackinghandle deklarieren.  
  
 [Deklaration eines CLR-Arrays](../dotnet/declaration-of-a-clr-array.md)  
 Erläutert das Deklarieren und Initialisieren eines Arrays.  
  
 [Änderungen in der Initialisierungsreihenfolge für Konstruktoren](../dotnet/changes-in-constructor-initialization-order.md)  
 Beschreibt wichtige Änderungen in der Initialisierungsreihenfolge für Konstruktoren Klasse an.  
  
 [Änderungen in der Destruktorsemantik](../dotnet/changes-in-destructor-semantics.md)  
 Erläutert nicht deterministischen, `Finalize` im Vergleich zu `Dispose`, Auswirkungen für Verweisobjekte, und Verwenden von einer expliziten `Finalize`.  
  
 **Hinweis:** die Erläuterung der Delegaten wird verzögert, bis [Delegaten und Ereignisse](../dotnet/delegates-and-events.md) um übergegeben mit Ereignis-Elemente innerhalb einer Klasse, die allgemeine Thema [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + C++ / CLI) ](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).  
  
## <a name="see-also"></a>Siehe auch  
 [C + c++ / CLI Migration Primer](../dotnet/cpp-cli-migration-primer.md)   
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Arrays](../windows/arrays-cpp-component-extensions.md)