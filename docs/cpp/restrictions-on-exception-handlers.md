---
title: Einschränkungen bei Ereignishandlern | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f739152b502a156dc62dfab279e5ad044cfff99
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32420203"
---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern
Die Haupteinschränkung bei der Verwendung von Ausnahmehandlern im Code besteht darin, dass Sie keine `goto`-Anweisung verwenden können, um in einen `__try`-Anweisungsblock zu wechseln. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Sie können aus einem `__try`-Anweisungsblock herausspringen und Ausnahmehandler nach Belieben schachteln.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)