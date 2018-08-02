---
title: Einschränkungen bei Beendigungshandlern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- termination handlers [C++], limitations
- restrictions, termination handlers
- try-catch keyword [C++], termination handlers
ms.assetid: 8b1cb481-303f-4e79-b409-57a002a9fa9e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ae16363956afc7cca853307ef2888846a02864d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461769"
---
# <a name="restrictions-on-termination-handlers"></a>Einschränkungen bei Beendigungshandlern
Können keine **Goto** gesprungen-Anweisung eine **__try** Anweisungsblock oder ein **__finally** Anweisungsblock. Stattdessen müssen Sie den Anweisungsblock über die normale Ablaufsteuerung eingeben. (Sie können jedoch direkt von einem **__try** Anweisungsblock.) Darüber hinaus können nicht geschachtelt keinen Ausnahmehandler oder Beendigungshandler innerhalb einer **__finally** Block.  
  
 Darüber hinaus erzeugen einige in einem Beendigungshandler zulässige Arten von Code fragliche Ergebnisse. Daher sollten Sie diese, wenn überhaupt, mit Vorsicht verwenden. Eine ist ein **Goto** -Anweisung, die von springt eine **__finally** Anweisungsblock. Wenn der Block als Teil der normalen Beendigung ausgeführt wird, passiert nichts Ungewöhnliches. Aber wenn das System den Stapel entlädt, wird das Entladen gestoppt, und die aktuelle Funktion erhält die Steuerung,als ob keine nicht ordnungsgemäße Beendigung vorläge.  
  
 Ein **zurückgeben** -Anweisung innerhalb einer **__finally** -Anweisungsblocks stellt ungefähr die gleiche Situation. Die Steuerung wird an den unmittelbaren Aufrufer der Funktion zurückgegeben, die den Beendigungshandler enthält. Wenn das System beim Entladen des Stapels war, wird dieser Prozess unterbrochen, und das Programm wird fortgesetzt, als wäre keine Ausnahme ausgelöst worden.  
  
## <a name="see-also"></a>Siehe auch  
 [Schreiben eines Beendigungshandlers](../cpp/writing-a-termination-handler.md)   
 [Strukturierte Ausnahmebehandlung (C/C++)](../cpp/structured-exception-handling-c-cpp.md)