---
title: system-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- system function
ms.assetid: 0786ccdc-20cd-4d96-b3d8-3230507c3066
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 51c9e9e348f1cd1fbae9612c2d2ad1988af3b009
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386734"
---
# <a name="system-function"></a>Systemfunktion
**ANSI 4.10.4.5** Die Inhalte und der Ausführmodus der Zeichenfolge durch die **system**-Funktion  
  
 Die **system**-Funktion führt einen internen Betriebssystembefehl oder eine EXE-, COM- (CMD in Windows NT) oder BAT-Datei aus einem C-Programm und nicht aus der Befehlszeile aus.  
  
 Die Systemfunktion durchsucht den Befehlsinterpreter, der in der Regel CMD.EXE im Windows NT-Betriebssystem oder COMMAND.COM in Windows ist. Die Systemfunktion gibt die Argumentzeichenfolge anschließend an den Befehlsinterpreter weiter.  
  
 Weitere Informationen finden Sie unter [system, _wsystem](../c-runtime-library/reference/system-wsystem.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Bibliotheksfunktionen](../c-language/library-functions.md)