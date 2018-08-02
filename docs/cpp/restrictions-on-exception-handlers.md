---
title: Einschränkungen bei Ereignishandlern | Microsoft-Dokumentation
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
ms.openlocfilehash: 8775f752a541d2a250e9c1c5a0c325b684335988
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464599"
---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern
Die haupteinschränkung bei Verwendung von ausnahmehandlern im Code ist, dass keine **Goto** gesprungen-Anweisung eine **__try** Anweisungsblock. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Können Sie direkt von einem **__try** Anweisung blockieren und Ausnahmehandler schachteln, wie Sie auswählen.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)