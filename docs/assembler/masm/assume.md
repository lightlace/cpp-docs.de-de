---
title: ANGENOMMEN | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: ASSUME
dev_langs: C++
helpviewer_keywords: ASSUME directive
ms.assetid: cd162070-aee9-4c65-babc-005c6cc73d7c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6046d19e628e75dee6e3f33b400c48dcbf317735
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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