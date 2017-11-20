---
title: "Einschränkungen bei Beendigungshandlern | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 593cb54298682c53f534e92f6553d86d2118d98b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="restrictions-on-termination-handlers"></a>Einschränkungen bei Beendigungshandlern
Sie können keine `goto`-Anweisung verwenden, um in einen `__try`-Anweisungsblock oder einen `__finally`-Anweisungsblock zu wechseln. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. (Sie können jedoch aus einem `__try`-Anweisungsblock herausspringen). Sie können auch keinen Ausnahmehandler oder Beendigungshandler innerhalb eines `__finally`-Blocks verschachteln.  
  
 Darüber hinaus erzeugen einige in einem Beendigungshandler zulässige Arten von Code fragliche Ergebnisse. Daher sollten Sie diese, wenn überhaupt, mit Vorsicht verwenden. Eine ist eine `goto`-Anweisung, die aus einem `__finally`-Anweisungsblock herausspringt. Wenn der Block als Teil der normalen Beendigung ausgeführt wird, passiert nichts Ungewöhnliches. Aber wenn das System den Stapel entlädt, wird das Entladen gestoppt, und die aktuelle Funktion erhält die Steuerung,als ob keine nicht ordnungsgemäße Beendigung vorläge.  
  
 Eine `return`-Anweisung innerhalb eines `__finally`-Anweisungsblocks stellt ungefähr die gleiche Situation dar. Die Steuerung wird an den unmittelbaren Aufrufer der Funktion zurückgegeben, die den Beendigungshandler enthält. Wenn das System beim Entladen des Stapels war, wird dieser Prozess unterbrochen, und das Programm wird fortgesetzt, als wäre keine Ausnahme ausgelöst worden.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)