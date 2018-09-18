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
ms.openlocfilehash: 29a462f83bff3bab158e9bcf9fa7947efb56a79b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46074473"
---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern

Die haupteinschränkung bei Verwendung von ausnahmehandlern im Code ist, dass keine **Goto** gesprungen-Anweisung eine **__try** Anweisungsblock. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Können Sie direkt von einem **__try** Anweisung blockieren und Ausnahmehandler schachteln, wie Sie auswählen.

## <a name="see-also"></a>Siehe auch

[Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)