---
title: ANGENOMMEN | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- ASSUME
dev_langs:
- C++
helpviewer_keywords:
- ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f8898895d2e107e522fe88dc954146d64e6f62b9
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
ms.locfileid: "32050635"
---
# <a name="assume"></a>ASSUME
Fehler beim Überprüfen der Registerwerte wird aktiviert.  
  
## <a name="syntax"></a>Syntax  
  
```  
ASSUME segregister:name [[, segregister:name]]...  
ASSUME dataregister:type [[, dataregister:type]]...  
ASSUME register:ERROR [[, register:ERROR]]...  
ASSUME [[register:]] NOTHING [[, register:NOTHING]]...  
```  
  
## <a name="remarks"></a>Hinweise  
 Nach einer `ASSUME` ist in Kraft getreten, überwacht der Assembler die Änderungen an den Werten der angegebenen. **Fehler** wird ein Fehler generiert, wenn die Registrierung verwendet wird. **NICHTS** entfernt fehlerüberprüfung zu registrieren. Sie können verschiedene Arten von Annahmen in einer einzelnen Anweisung kombinieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Anweisungen – Referenz](../../assembler/masm/directives-reference.md)