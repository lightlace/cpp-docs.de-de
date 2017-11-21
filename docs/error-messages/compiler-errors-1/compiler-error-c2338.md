---
title: Compilerfehler C2338 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2338
dev_langs: C++
helpviewer_keywords: C2338
ms.assetid: 49bba575-1de4-4963-86c6-ce3226a2ba51
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3b5f8773daa61b2ac7703b1ee0e5672818278e87
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2338"></a>Compilerfehler C2338  
  
> *Fehlermeldung*  
  
Dieser Fehler kann verursacht werden, indem eine `static_assert` Fehler während der Kompilierung. Die Meldung wird angegeben, durch die `static_assert` Parameter.   
  
Diese Fehlermeldung kann auch von externen Anbietern für den Compiler generiert werden. In den meisten Fällen werden diese Fehler durch eine Attributanbieter-DLL, z. B. ATLPROV gemeldet. Einige häufig verwendete Formen von dieser Nachricht gehören:

> "*Attribut*" Atl-Attributanbieter: Fehler ATL*Anzahl* *Nachricht*  
  
> Falsche Verwendung des Attributs "*Attribut*"
  
> "*Verwendung*': falsches Format für das Attribut"Nutzung"  
  
Dieser Fehler häufig nicht behebbar sind, und ein schwerwiegender Compilerfehler gefolgt werden können.  
  
Um diese Probleme zu beheben, korrigieren Sie den Attributen aus. In einigen Fällen müssen z. B. Attributparameter deklariert werden, bevor sie verwendet werden können. Wenn eine ATL-Fehlernummer angegeben wird, überprüfen Sie die Dokumentation für Weitere Informationen zu diesem Fehler.  
