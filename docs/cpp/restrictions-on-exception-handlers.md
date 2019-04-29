---
title: Einschränkungen bei Ereignishandlern
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 7d5bf20da61f4b9f5012b7f2aab932dfc904c302
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403359"
---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern

Die haupteinschränkung bei Verwendung von ausnahmehandlern im Code ist, dass keine **Goto** gesprungen-Anweisung eine **__try** Anweisungsblock. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Können Sie direkt von einem **__try** Anweisung blockieren und Ausnahmehandler schachteln, wie Sie auswählen.

## <a name="see-also"></a>Siehe auch

[Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)<br/>
[Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)