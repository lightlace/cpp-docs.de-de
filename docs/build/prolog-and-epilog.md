---
title: "Prolog und Epilog | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Prolog und Epilog
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede Funktion, die Stapelspeicher reserviert, andere Funktionen aufruft, nicht veränderliche Register speichert oder Ausnahmebehandlungen verwendet, muss über einen Prolog verfügen, dessen Adresseneinschränkungen in den Entladedaten beschrieben werden, die dem entsprechenden Funktionstabelleneintrag zugeordnet sind \(siehe [Ausnahmebehandlung \(x64\)](../build/exception-handling-x64.md)\).  Der Prolog speichert gegebebenfalls Argumentregister an ihren Basisadressen, legt nicht veränderliche Register auf den Stapel, reserviert den festen Teil des Stapels für lokale Variablen und temporäre Werte und legt optional einen Framezeiger fest.  Die zugeordneten Entladedaten müssen die Aktion des Prologs beschreiben und die erforderlichen Informationen bereitstellen, um die Auswirkungen des Prologs rückgängig machen zu können.  
  
 Wenn die feste Zuweisung im Stapel länger als eine Seite ist \(d. h. größer als 4096 Byte\), kann die Stapelzuweisung mehr als eine virtuellen Speicherseite umfassen. Daher muss die Zuweisung überprüft werden, bevor die tatsächliche Zuweisung erfolgt.  Zu diesem Zweck ist eine spezielle Routine vorhanden, die vom Prolog aufgerufen werden kann und die Argumentregister nicht verändert.  
  
 Die bevorzugte Methode zum Speichern nicht veränderlicher Register besteht darin, diese vor der festen Stapelzuweisung auf den Stapel zu verschieben.  Wenn die feste Stapelzuweisung vor dem Speichern der nicht veränderlichen Register ausgeführt würde, wäre sehr wahrscheinlich eine 32\-Bit\-Verschiebung für die Adressierung des gespeicherten Registerbereichs erforderlich \(Berichten zufolge sind push\-Vorgänge für Register genauso schnell wie Verschiebungen und sollten dies auch in absehbarer Zeit bleiben, trotz der implizierten Abhängigkeit zwischen push\-Vorgängen\).  Nicht veränderliche Register können in jeder Reihenfolge gespeichert werden.  Die erste Verwendung eines nicht veränderlichen Registers im Prolog muss jedoch darin bestehen, es zu speichern.  
  
 Der Code für einen typischen Prolog könnte folgendermaßen aussehen:  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
sub      RSP, fixed-allocation-size  
lea      R13, 128[RSP]  
...  
```  
  
 Dieser Prolog speichert das Argumentregister RCX an seinem Basisspeicherort, speichert die nicht veränderlichen Register R13\-R15, reserviert den festen Teil des Stapelrahmens und legt einen Framezeiger fest, der auf 128 Byte des festen Zuweisungsbereichs verweist.  Durch Verwendung eines Offsets kann ein größerer Teil des festen Zuweisungsbereichs mit 1\-Byte\-Offsets adressiert werden.  
  
 Wenn die feste Zuweisungsgröße einer Speicherseite entspricht oder größer ist, muss eine Hilfsfunktion aufgerufen werden, bevor RSP geändert wird.  Diese Hilfsfunktion, \_\_chkstk, ist verantwortlich für die Überprüfung des zuzuweisenden Stapelbereichs, um sicherzustellen, dass der Stapel richtig erweitert wird.  In diesem Fall wäre das Prologbeispiel:  
  
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
  
 Die \_\_chkstk\-Hilfsfunktion ändert neben R10, R11 und den Bedingungscodes keine anderen Register.  Insbesondere wird RAX unverändert zurückgegeben, und alle nicht veränderlichen Register und Argumentübergabe\-Register bleiben unverändert.  
  
 Epilogcode ist am Ende jeder Funktion vorhanden.  Während es normalerweise nur einen Prolog gibt, kann es hier viele Epiloge geben.  Der Epilogcode reduziert den Stapel auf seine feste Zuweisungsgröße \(falls erforderlich\), hebt die feste Stapelzuweisung auf, stellt nicht veränderliche Register durch Auslesen ihrer gespeicherten Werte aus dem Stapel wieder her und kehrt zurück.  
  
 Der Epilogcode muss strikten Regeln folgen, damit der Entladecode zuverlässig durch Ausnahmen und Interrupts entladen kann.  Dadurch wird die Menge der erforderlichen Entladedaten reduziert, da keine zusätzlichen Daten zum Beschreiben der einzelnen Epiloge erforderlich sind.  Stattdessen kann der Entladecode bestimmen, dass ein Epilog ausgeführt wird, indem zur Erkennung eines Epilogs der Codestream vorwärts durchsucht wird.  
  
 Wenn in der Funktion kein Framezeiger verwendet wird, muss der Epilog zuerst die Zuweisung für den ersten Teil des Stapels aufheben, dann werden die nicht veränderlichen Register ausgelesen und die Steuerung wird an die aufrufende Funktion zurückgegeben.  Beispiel:  
  
```  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Wenn in der Funktion ein Framezeiger verwendet wird, muss der Stapel vor Ausführung des Epilogs auf seine feste Zuweisung reduziert werden.  Dies ist technisch gesehen nicht Teil des Epilogs.  Beispielsweise könnte der folgende Epilog verwendet werden, um den vorher verwendeten Prolog rückgängig zu machen:  
  
```  
lea      RSP, -128[R13]  
; epilogue proper starts here  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 In der Praxis gibt es bei Verwendung eines Framezeigers keinen Grund, RSP in zwei Schritten anzupassen, daher würde stattdessen der folgende Epilog verwendet:  
  
```  
lea      RSP, fixed-allocation-size – 128[R13]  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Dies sind die einzigen gültigen Formen eines Epilogs.  Ein Epilog muss entweder aus `add RSP,constant` oder `lea RSP,constant[FPReg]` gefolgt von einer Reihe von 0 \(null\) oder mehr 8\-Byte\-pop\-Vorgängen sowie einer return\- oder jmp\-Anweisung bestehen.  \(Nicht alle jmp\-Anweisungen sind im Epilog zugelassen.  Diese sind eingeschränkt auf jmp\-Anweisungen der Klasse mit ModRM\-Speicherverweisen, bei denen der ModRM\-mod\-Feldwert 00 ist.  Die Verwendung von jmp\-Anweisungen mit dem ModRM\-mod\-Feldwert 01 oder 10 ist im Epilog unzulässig.  Weitere Informationen zu den zulässigen ModRM\-Verweisen finden Sie in Tabelle A\-15 im AMD x86\-64 Architecture Programmer’s Manual Volume 3: General Purpose and System Instructions.\)  Kein anderer Code kann verwendet werden.  Insbesondere kann innerhalb eines Epilogs nichts geplant werden, auch nicht das Laden eines Rückgabewerts.  
  
 Beachten Sie, dass der Epilog `add RSP,constant` zum Aufheben der Zuweisung für den festen Teil des Stapels verwenden muss, wenn kein Framezeiger verwendet wird.  Es kann stattdessen nicht `lea RSP,constant[RSP]` verwendet werden.  Diese Einschränkung ist vorhanden, damit der Entladecode beim Suchen nach Epilogen weniger Muster zu erkennen hat.  
  
 Durch Befolgen dieser Regeln kann der Entladecode ermitteln, ob gegenwärtig ein Epilog ausgeführt wird, und die Ausführung des restlichen Epilogs simulieren, um eine Neuerstellung des Kontexts der aufrufenden Funktion zu ermöglichen.  
  
## Siehe auch  
 [x64\-Softwarekonventionen](../build/x64-software-conventions.md)