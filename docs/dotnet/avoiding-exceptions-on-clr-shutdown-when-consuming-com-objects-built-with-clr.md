---
title: Vermeiden mit / Clr erstellte COM-Objekte ausgelöste Ausnahmen
ms.date: 11/04/2016
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
ms.openlocfilehash: 23af1d8b48a6579b8cc20261691c1f090dc858a2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633440"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit /clr erstellte COM-Objekte verwendet werden

Sobald die common Language Runtime (CLR) heruntergefahren-Modus wechselt, haben systemeigene Funktionen den eingeschränkten Zugriff auf CLR-Dienste. Beim Versuch, rufen Sie die Version auf ein COM-Objekt mit kompiliert **"/ CLR"**, geht die CLR in systemeigenen Code, und klicken Sie dann wechselt zurück in verwaltetem Code, den Aufruf von IUnknown:: Release-service (die in verwaltetem Code definiert ist). Da sie für das Herunterfahren betrieben wird verhindert, dass die CLR den Aufruf in verwaltetem Code.

Um dies zu beheben, stellen Sie sicher, dass Destruktoren aufgerufen von Release-Methoden nur systemeigenen Code enthalten.

## <a name="see-also"></a>Siehe auch

[Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)