---
title: Vermeiden von Ausnahmen, die von erstellte COM-Objekte mit Clr-| Microsoft Docs
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
ms.openlocfilehash: 0efd2af7eb4bf8a70bff983d627f802f1976c6ba
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103511"
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit /clr erstellte COM-Objekte verwendet werden
Sobald die common Language Runtime (CLR) heruntergefahren Modus wechselt, systemeigene Funktionen Zugriff auf CLR-Dienste eingeschränkt. Beim Versuch, rufen Sie Release auf ein COM-Objekt mit kompiliert **"/ CLR"**, geht die CLR in systemeigenen Code und wechselt anschließend zurück in verwaltetem Code Verarbeiten von der IUnknown:: Release-Aufruf (die in verwaltetem Code definiert ist). Die CLR wird verhindert, dass den Aufruf an verwalteten Code, da es sich im Modus für das Herunterfahren befindet.  
  
 Um dies zu beheben, stellen Sie sicher, dass Destruktoren von Version Methoden aufgerufen nur systemeigenen Code enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)