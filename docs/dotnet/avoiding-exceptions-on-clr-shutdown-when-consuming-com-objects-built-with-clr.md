---
title: Vermeiden von Ausnahmen, die von erstellte COM-Objekte mit Clr-| Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], CLR shutdown exceptions
- /clr compiler option [C++], CLR shutdown exceptions
- mixed assemblies [C++], CLR shutdown exceptions
- /clr compiler option [C++], COM objects
- interoperability [C++], CLR shutdown exceptions
- CLR shutdown exceptions [C++]
ms.assetid: 41249d83-4b51-4e46-866f-27f475f2498c
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 430420a62915d3378dae863c20c00e3b398ecb3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="avoiding-exceptions-on-clr-shutdown-when-consuming-com-objects-built-with-clr"></a>Vermeiden von Ausnahmen beim Herunterfahren der CLR, wenn mit /clr erstellte COM-Objekte verwendet werden
Sobald die common Language Runtime (CLR) heruntergefahren Modus wechselt, systemeigene Funktionen Zugriff auf CLR-Dienste eingeschränkt. Beim Versuch, rufen Sie Release auf ein COM-Objekt mit kompiliert **"/ CLR"**, geht die CLR in systemeigenen Code und wechselt anschließend zurück in verwaltetem Code Verarbeiten von der IUnknown:: Release-Aufruf (die in verwaltetem Code definiert ist). Die CLR wird verhindert, dass den Aufruf an verwalteten Code, da es sich im Modus für das Herunterfahren befindet.  
  
 Um dies zu beheben, stellen Sie sicher, dass Destruktoren von Version Methoden aufgerufen nur systemeigenen Code enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Gemischte (native und verwaltete) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)