---
title: Schwerwiegender Fehler C1900 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1900
dev_langs:
- C++
helpviewer_keywords:
- C1900
ms.assetid: 3aaa583b-4c1a-45de-aa34-527d806f2cb5
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3b64061401189fb37f28492fbffe1e9941e8aab8
ms.contentlocale: de-de
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1900"></a>Schwerwiegender Fehler C1900
Konflikt zwischen 'tool1', Version 'Nummer1', und 'tool2', Version 'Nummer2'  
  
 In verschiedenen Durchläufen des Compilers ausgeführte Tools stimmen nicht überein. ***"number1"*** und ***"number2"*** finden Sie in die Datumsangaben der Dateien. Z. B. führt in Durchgang 1 durch das Compiler-front End (c1.dll) ausgeführt und in Durchgang 2 führt der Compiler-back-End (c2.dll) aus. Die Datumsangaben der Dateien müssen übereinstimmen.  
  
 Um dieses Problem zu beheben, stellen Sie sicher, dass alle Aktualisierungen auf Visual Studio angewendet wurden. Wenn das Problem weiterhin besteht, verwenden Sie **Programme und Funktionen** in der Windows-Systemsteuerung reparieren oder neu installieren von Visual Studio.
