---
title: CString-Ausnahmebereinigung | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- CString objects, exceptions
- exception handling, cleanup code
ms.assetid: 28b9ce70-be63-4a0d-92a8-44bbfbc95e83
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 68fb6f60c46ff5094e1b7a578a47646f42cea79e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cstring-exception-cleanup"></a>CString-Ausnahmebereinigung
In früheren Versionen von MFC war es wichtig, dass Sie bereinigen [CString](../atl-mfc-shared/reference/cstringt-class.md) Objekte nach der Verwendung. Mit MFC, Version 3.0 und höher ist eine explizite Bereinigung nicht mehr erforderlich.  
  
 Unter der C++-Ausnahmebehandlungsmechanismus, die jetzt MFC verwendet, müssen Sie keinen Cleanup nach einer Ausnahme kümmern. Eine Beschreibung dazu, wie C++ "entlädt" im Stapel nach dem eine Ausnahme abgefangen wird, finden Sie unter [die Try-, catch- und throw-Anweisungen](../cpp/try-throw-and-catch-statements-cpp.md). Auch wenn Sie die MFC-Bibliothek verwenden **versuchen**/**CATCH** Makros anstelle von C++-Schlüsselwörter **versuchen** und **catch**, verwendet MFC C++ Ausnahmemechanismus, damit Sie immer noch müssen nicht explizit bereinigen.  
  
## <a name="see-also"></a>Siehe auch  
 [Zeichenfolgen (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Ausnahmebehandlung](../mfc/exception-handling-in-mfc.md)

