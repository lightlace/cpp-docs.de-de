---
title: "Einschränkungen bei Ereignishandlern | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling, exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 1806c737b9adfcefbe6417fda92ddc054094d4db
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern
Die Haupteinschränkung bei der Verwendung von Ausnahmehandlern im Code besteht darin, dass Sie keine `goto`-Anweisung verwenden können, um in einen `__try`-Anweisungsblock zu wechseln. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Sie können aus einem `__try`-Anweisungsblock herausspringen und Ausnahmehandler nach Belieben schachteln.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)
