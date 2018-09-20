---
title: Vermeiden von Ausnahmen, die mit / Clr erstellte COM-Objekte ausgelöste | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 687585d0b25c64f5575646de3cd4823e0a89988e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408971"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit /clr erstellte COM-Objekte verwendet werden

Sobald die common Language Runtime (CLR) heruntergefahren-Modus wechselt, haben systemeigene Funktionen den eingeschränkten Zugriff auf CLR-Dienste. Beim Versuch, rufen Sie die Version auf ein COM-Objekt mit kompiliert **"/ CLR"**, geht die CLR in systemeigenen Code, und klicken Sie dann wechselt zurück in verwaltetem Code, den Aufruf von IUnknown:: Release-service (die in verwaltetem Code definiert ist). Da sie für das Herunterfahren betrieben wird verhindert, dass die CLR den Aufruf in verwaltetem Code.

Um dies zu beheben, stellen Sie sicher, dass Destruktoren aufgerufen von Release-Methoden nur systemeigenen Code enthalten.

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)