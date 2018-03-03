---
title: Compilerfehler Warnung C4746 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f92bae0e75d9a09de874cd999c044e703b3f3171
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4746"></a>Compilerfehler Warnung C4746
flüchtige Zugriff des "\<Ausdruck >" / volatile des unterliegt: [Iso &#124; ms] festlegen; in Betracht __iso_volatile_load/Store systeminterne Funktionen.  
  
 C4746 wird ausgegeben, wenn eine flüchtige Variable direkt zugegriffen wird. Es richtet sich an, damit Entwickler codespeicherorte zu identifizieren, die von bestimmten derzeit angegebenen volatile Modells betroffen sind (die kann gesteuert werden, mit der [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) (Compileroption)). Insbesondere kann es sein hilfreich bei der Suche vom Compiler generierte hardwarearbeitsspeicherbarrieren, wenn /volatile:ms verwendet wird.  
  
 Die __iso_volatile_load/Store Intrinsics kann verwendet werden, um explizit flüchtigen Speicher zugreifen, ohne von flüchtigen Modell betroffen sind. Verwenden diese systeminternen Funktionen wird nicht C4746 ausgelöst.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .