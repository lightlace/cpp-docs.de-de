---
title: Werttypen und ihr Verhalten (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: value types
ms.assetid: 5cb872a6-1e0a-429d-853d-df4ab47e8f2a
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: ccb26e1f054e6914f24982b36f6655fa62fc9f99
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="value-types-and-their-behaviors-ccli"></a>Werttypen und ihr Verhalten (C++/CLI)
Werttypen sind für Visual C++ auf verschiedene Arten von Managed Extensions for C++ geändert. In diesem Abschnitt untersuchen wir die CLR-Enumerationstyp und die Klasse Werttyp ist, zusammen mit einem Blick auf Boxing und den Zugriff auf die geschachtelte Instanz auf dem CLR-Heap sowie einen Blick auf innerer und fester Zeiger. Es wurden umfassende sprachänderungen in diesem Bereich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [CLR-Enumerationstyp](../dotnet/value-types-and-their-behaviors-cpp-cli.md)  
 Erläutert die Änderungen in der Deklaration und das Verhalten von Enumerationen.  
  
 [Implizites Boxing von Werttypen](../dotnet/implicit-boxing-of-value-types.md)  
 Erläutert die Motivation für implizites Boxing von Werttypen und die ein Änderungen im Verhalten.  
  
 [Ein Trackinghandle für einen geschachtelten Wert](../dotnet/a-tracking-handle-to-a-boxed-value.md)  
 Erläutert, wie implizites Boxing des Werts Typen ein Trackinghandle für das Objekt durch Boxing konvertierten Wert ergibt.  
  
 [Werttypsemantik](../dotnet/value-type-semantics.md)  
 Werden Änderungen an Werttypsemantik, einschließlich geerbte virtuelle Methoden, die Standard-Klasse, Konstruktoren, die inneren Zeigern und Festhalten von Zeigern erläutert.  
  
## <a name="see-also"></a>Siehe auch  
 [C + c++ / CLI Migration Primer](../dotnet/cpp-cli-migration-primer.md)   
 [Klassen und Strukturen](../windows/classes-and-structs-cpp-component-extensions.md)