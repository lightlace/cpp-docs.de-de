---
title: Prolog und Epilog | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 700b467065d17a61dcfabf9dcaa6577a7ecffc11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="prolog-and-epilog"></a>Prolog und Epilog
Jede Funktion, die Stapelspeicher zuweist, in Aufrufe an andere Funktionen, um nicht flüchtigen Register speichert oder mithilfe der Ausnahmebehandlung benötigen einen Prolog, deren Adresse Limits werden in der jeweiligen Funktion Tabelleneintrag zugeordneten Entladedaten beschrieben (siehe [Ausnahmebehandlung (x64)](../build/exception-handling-x64.md)). Prolog speichert Argument Registern in der ihre Privatadressen ggf. schiebt nicht flüchtigen Register auf den Stapel, festen Bestandteil des Stapels für "lokal" und die temporären Dateien, die zuweist und stellt optional ein Frame-Pointer her. Die zugeordnete Entladedaten müssen die Aktion der Prolog beschreiben, und geben Sie müssen die erforderlichen Informationen für die Auswirkung der Prologcode rückgängig zu machen.  
  
 Wenn die feste Verteilung im Stapel mehr als eine Seite ist (d. h. größer als 4096 Bytes), ist es möglich, dass die Stack-gesamtzuordnung kann mehr als eine virtuelle Speicherseite umfassen, und daher die Zuweisung überprüft werden muss, bevor er tatsächlich zugeordnet ist. Zu diesem Zweck wird eine spezielle Routine, die aus der Prolog aufgerufen werden kann und die nicht zerstört keines der Argument-Register, bereitgestellt.  
  
 Die bevorzugte Methode zum Speichern von nicht flüchtigen Register werden auf den Stapel vor dem festen stapelzuordnung verschieben. Wenn die festen stapelzuordnung ausgeführt wurden, bevor nicht flüchtigen Register gespeichert wurden, wird wahrscheinlich eine 32-Bit-Verschiebung Adresse erforderlich wäre registrieren gespeicherten Bereich (installiert, Push-Vorgänge von Registern sind nur so schnell wie verschoben und bleiben sollten für absehbare trotz der implizite Abhängigkeit zwischen Push-Vorgänge). Nicht volatile Register können in beliebiger Reihenfolge gespeichert werden. Allerdings muss der erste Verwendung der einen nicht flüchtigen Register im Prolog sein, um ihn zu speichern.  
  
 Der Code für einen normalen Prolog kann Folgendes sein:  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
sub      RSP, fixed-allocation-size  
lea      R13, 128[RSP]  
...  
```  
  
 Dieser Prolog speichert das Argument Register RCX an ihrem privaten Speicherort, speichert nicht volatil Register R13-R15, reserviert den festen Teil des Stapelrahmens und stellt die Frame-Pointer, der von 128 Byte in den Bereich "feste Zuweisung" zeigt her. Mit einem Offset kann mehrere des festen Zuweisungsbereichs mit einem Byte-Offsets behandelt werden.  
  
 Wenn die festen Zuordnungsgröße größer als oder gleich einer Seite des Arbeitsspeichers ist, muss eine Hilfsfunktion aufgerufen werden, vor der Änderung RSP. Diese Hilfsfunktion, __chkstk, ist verantwortlich für die Überprüfung des zu zuzuweisenden Stapelbereichs, um sicherzustellen, dass der Stapel richtig erweitert wird. Im vorherigen Beispiel der Prolog wäre in diesem Fall stattdessen:  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
mov      RAX,  fixed-allocation-size  
call   __chkstk  
sub      RSP, RAX  
lea      R13, 128[RSP]  
...  
```  
  
 Das Hilfsobjekt __chkstk wird anderen Register R10, R11 und den Bedingungscodes nicht geändert werden. Insbesondere wird RAX unverändert und lassen Sie alle nicht flüchtigen Register und Argumentübergabe Register unverändert bleiben sollen.  
  
 Epilogcode ist am Ende jeder Funktion vorhanden. Es ist normalerweise nur einen Prolog, können hier viele Epiloge geben vorhanden sein. Epilogcode kürzt den Stapel, um seine festen Zuordnungsgröße (falls erforderlich), hebt die Zuordnung der festen stapelzuordnung, wird Sie nicht flüchtigen Register wiederhergestellt, indem Sie ihre gespeicherten Werte aus dem Stapel herunternehmen und zurückgibt.  
  
 Der Epilogcode muss strenge Regeln für die entladungscode zu zuverlässig Entladung durch Ausnahmen und Interrupts folgen. Dies reduziert die Menge der Entladedaten erforderlich, da keine zusätzlichen Daten zum Beschreiben der einzelnen Epiloge erforderlich ist. Stattdessen kann der entladungscode bestimmen, dass ein Epilog ausgeführt wird, durch das Scannen Rollforward über einen Codestream, um einen Epilog zu identifizieren.  
  
 Wenn keine Frame-Pointer, in verwendet wird der Funktion, und klicken Sie dann auf der Epilog muss zuerst die Zuweisung festen Bestandteil des Stapels nicht flüchtigen Register per pop ausgelesen werden und wird die Steuerung an die aufrufende Funktion zurückgegeben. Ein auf ein Objekt angewendeter  
  
```  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Wenn der Frame-Pointer in der Funktion verwendet wird, muss der Stapel auf seine feste Zuweisung vor der Ausführung des Epilogs gekürzt werden. Dies ist technisch nicht Teil des Epilogs. Z. B. konnte der folgende Epilog verwendet werden, um den vorher verwendeten Prolog rückgängig zu machen:  
  
```  
lea      RSP, -128[R13]  
; epilogue proper starts here  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 In der Praxis Wenn Frame-Pointer verwendet wird, besteht kein guter Grund RSP in zwei Schritten anpassen, damit die folgenden Epilog stattdessen verwendet werden würde:  
  
```  
lea      RSP, fixed-allocation-size - 128[R13]  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Dies sind die einzigen gültigen Formen eines Epilogs. Es muss entweder bestehen einer `add RSP,constant` oder `lea RSP,constant[FPReg]`, gefolgt von einer Reihe von NULL oder mehr 8-Byte-Register und einen Rückgabecode oder eine jmp-Anweisung. (Nur eine Teilmenge der Jmp-Anweisungen in der Epilog zulässig sind. Diese sind ausschließlich der Klasse des Jmps mit ModRM Speicherreferenzen, in denen ModRM mod Feldwert 00. Die Verwendung von Jmps in der Epilog mit ModRM mod Feldwert 01 oder 10 ist nicht zulässig. Tabelle finden Sie unter A-15 in der AMD X86 64 Architecture Programmer's Manual Volume 3: Allzweckregister und System-Anweisungen, um weitere Informationen zu den zulässigen ModRM-verweisen.). Kann kein anderer Code angezeigt werden. Insbesondere kann nichts innerhalb eines Epilogs, z. B. das Laden eines Rückgabewerts geplant werden.  
  
 Beachten Sie, dass, wenn der Frame-Pointer nicht verwendet wird, der Epilog `add RSP,constant` festen Bestandteil des Stapels aufgehoben. Es sind nicht verwenden `lea RSP,constant[RSP]` stattdessen. Diese Einschränkung ist vorhanden, sodass der entladungscode weniger Muster zu erkennen, beim Suchen nach epilogen hat.  
  
 Befolgen diese Regeln können entladungscode, um zu bestimmen, dass ein Epilog derzeit ausgeführt wird und Ausführung der Rest des Epilogs zu ermöglichen, den Kontext der aufrufenden Funktion Neuerstellen zu simulieren.  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)