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
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f9e55ba9c36fdbc5f3c19e7ad81373599ab138e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern
Die Haupteinschränkung bei der Verwendung von Ausnahmehandlern im Code besteht darin, dass Sie keine `goto`-Anweisung verwenden können, um in einen `__try`-Anweisungsblock zu wechseln. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Sie können aus einem `__try`-Anweisungsblock herausspringen und Ausnahmehandler nach Belieben schachteln.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)