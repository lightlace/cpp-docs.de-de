---
title: Compilerwarnung (Stufen 1 und 4) C4115 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4115
dev_langs:
- C++
helpviewer_keywords:
- C4115
ms.assetid: f3f94e72-fc49-4d09-b3e7-23d68e61152f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ec1c4377c2b7670b9d934d13d09bc5336fe5f30b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-1-and-4-c4115"></a>Compilerwarnung (Stufen 1 und 4) C4115
'Typ': Benannte Typdefinition in runden Klammern  
  
 Das angegebene Symbol wird verwendet, um eine Struktur, Union oder einen Aufzählungstyp innerhalb eines Klammerausdrucks zu definieren. Der Gültigkeitsbereich der Definition ist möglicherweise unerwartet.  
  
 Bei einem C-Funktionsaufruf weist die Definition einen globalen Gültigkeitsbereich auf. In einem C++-Aufruf weist die Definition denselben Gültigkeitsbereich wie die aufgerufene Funktion auf.  
  
 Diese Warnung kann auch durch Deklaratoren in Klammern (z. B. Prototypen) verursacht werden, die keine Ausdrücke in Klammern sind.  
  
 Dies ist eine Warnung der Stufe 1 für C++- und C#-Programme, die mit ANSI-Kompatibilität (/Za) kompiliert werden. Andernfalls handelt es sich um eine Warnung der Stufe 3.