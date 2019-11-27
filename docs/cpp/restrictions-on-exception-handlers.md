---
title: Einschränkungen bei Ereignishandlern
ms.date: 11/04/2016
helpviewer_keywords:
- restrictions, exception handlers
- exception handling [C++], exception handlers
ms.assetid: 31d63524-0e8c-419f-b87c-061f4c0ea470
ms.openlocfilehash: 030d444443b3a6e3e2e0ac0e015619046a76d562
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245155"
---
# <a name="restrictions-on-exception-handlers"></a>Einschränkungen bei Ereignishandlern

Die Prinzipal Einschränkung bei der Verwendung von Ausnahme Handlern im Code besteht darin, dass Sie keine **goto** -Anweisung verwenden können, um in einen **__try** Anweisungsblock zu springen. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. Sie können aus einem **__try** -Anweisungsblock springen und Ausnahmehandler bei der Auswahl Schachteln.

## <a name="see-also"></a>Siehe auch

[Schreiben eines Ausnahmehandlers](../cpp/writing-an-exception-handler.md)<br/>
[Structured Exception Handling (C/C++)](../cpp/structured-exception-handling-c-cpp.md)