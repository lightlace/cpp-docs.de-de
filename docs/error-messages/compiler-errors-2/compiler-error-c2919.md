---
title: Compilerfehler C2919 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2919
dev_langs: C++
helpviewer_keywords: C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a70b679d4add5fa4ad2904e3c0d103e1c8881280
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2919"></a>Compilerfehler C2919
'type': Operatoren können nicht direkt auf der veröffentlichten Oberfläche eines WinRT-Typs verwendet werden.  
  
 Das Windows-Runtime-Typsystem unterstützt nicht die Operatormemberfunktionen auf der veröffentlichten Oberfläche eines Typs. Dies liegt daran, weil nicht alle Sprachen Operatormemberfunktionen verwenden können. Sie können private oder interne Operatormemberfunktionen erstellen, die über C++-Code in derselben Klasse oder Kompilationskomponente aufgerufen werden können.  
  
 Entfernen Sie zum Beheben dieses Problems die Operatormemberfunktion aus der öffentlichen Schnittstelle, oder ändern Sie sie in eine benannte Memberfunktion. Benennen Sie die Memberfunktion beispielsweise anstelle von `operator==` in `Equals` um.