---
title: system-Funktion | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 16d1bf59dfd4b3ef5f037aed9c0f6febfdf1a2e8
ms.openlocfilehash: 965cca807ddbe9f0eb31144f75a7e3c6e4a80e77
ms.contentlocale: de-de
ms.lasthandoff: 10/09/2017

---
# <a name="system-function"></a>Systemfunktion
**ANSI 4.10.4.5** Die Inhalte und der Ausführmodus der Zeichenfolge durch die **system**-Funktion  
  
 Die **system**-Funktion führt einen internen Betriebssystembefehl oder eine EXE-, COM- (CMD in Windows NT) oder BAT-Datei aus einem C-Programm und nicht aus der Befehlszeile aus.  
  
 Die Systemfunktion durchsucht den Befehlsinterpreter, der in der Regel CMD.EXE im Windows NT-Betriebssystem oder COMMAND.COM in Windows ist. Die Systemfunktion gibt die Argumentzeichenfolge anschließend an den Befehlsinterpreter weiter.  
  
 Weitere Informationen finden Sie unter [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)
