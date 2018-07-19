---
title: Volatile (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- volatile_cpp
dev_langs:
- C++
helpviewer_keywords:
- interrupt handlers and volatile keyword [C++]
- volatile keyword [C++]
- volatile objects
- objects [C++], volatile
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ae3419cc7df0b9ed436981d5e845764a762c8ee8
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940966"
---
# <a name="volatile-c"></a>volatile (C++)
Ein Typqualifizierer, den Sie verwenden können, um zu deklarieren, dass ein Objekt im Programm von der Hardware geändert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
volatile declarator ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) Compilerschalter ändern, wie der Compiler dieses Schlüsselwort interpretiert.  
  
 Visual Studio interpretiert das **flüchtige** Schlüsselwort je nach der Zielarchitektur unterschiedlich. Für ARM, wenn kein **/volatile** -Compileroption angegeben ist, führt der Compiler wie **/volatile:iso** wurden angegeben. Architekturen als ARM, wenn kein **/volatile** -Compileroption angegeben ist, führt der Compiler wie **angegebenem** angegeben wurden; aus diesem Grund für Architekturen außer ARM wir stark Es wird empfohlen, die Sie angeben **/volatile:iso**, und explizite Synchronisierungsprimitiven und systeminterne Compilerfunktionen verwenden, wenn Sie mit Arbeitsspeicher arbeiten, der threadübergreifend bereitgestellt wird.  
  
 Sie können die **flüchtige** Qualifizierer, der Zugriff auf Speicheradressen zu ermöglichen, die von asynchronen Prozessen wie interrupthandlern verwendet werden.  
  
 Wenn **flüchtige** wird verwendet, auf eine Variable, die auch die ["__restrict"](../cpp/extension-restrict.md) -Schlüsselwort, **flüchtige** hat Vorrang vor.  
  
 Wenn eine **Struktur** Member wird als markiert **flüchtige**, klicken Sie dann **flüchtige** wird an die gesamte Struktur weitergegeben. Wenn eine Struktur keine Länge, die kopiert werden kann, in der aktuellen Architektur mithilfe einer Anweisung **flüchtige** möglicherweise vollständig verloren gehen, auf dieser Struktur.  
  
 Die **flüchtige** Schlüsselwort möglicherweise keine Auswirkungen auf ein Feld, wenn eine der folgenden Bedingungen zutrifft:  
  
-   Die Länge des flüchtigen Felds überschreitet die maximale Größe, die in der aktuellen Architektur mithilfe einer Anweisung kopiert werden kann.  
  
-   Die Länge der äußersten enthaltenen **Struktur**– oder wenn sie ein Mitglied einer möglicherweise geschachtelten ist **Struktur**– überschreitet die maximale Größe, die in der aktuellen Architektur mithilfe einer Anweisung kopiert werden kann.  
  
 Obwohl der Prozessor nicht anordnet Speicherzugriffe neu anzuordnen, müssen anordnet Variablen als gekennzeichnet sein **flüchtige** um sicherzustellen, dass der Compiler nicht den Arbeitsspeicher neu zugreift.  
  
 Objekte, die als deklariert sind **flüchtige** werden in bestimmten Optimierungen nicht verwendet, da ihre Werte jederzeit ändern können.  Das System liest bei jeder Anforderung den aktuellen Wert eines flüchtigen Objekts, selbst wenn eine vorherige Anweisung bereits den Wert des gleichen Objekts abgefragt hatte.  Außerdem wird der Wert des Objekts sofort durch Zuweisung geschrieben.  
  
## <a name="iso-compliant"></a>ISO-Kompatibilität  
 Wenn Sie mit der C#-Schlüsselwort "volatile" vertraut sind oder mit dem Verhalten von vertraut sind **flüchtige** in früheren Versionen von Visual C++, denken Sie daran, die der C ++ 11 ISO-Standard **flüchtige** -Schlüsselwort ist anders und wird in Visual Studio unterstützt bei der [/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption angegeben ist. (In ARM ist es standardmäßig festgelegt). Die **flüchtige** -Schlüsselwort in C ++ 11 ISO-Standardcode ist nur für Hardwarezugriffe verwendet werden nicht für die Kommunikation zwischen Threads verwenden. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Std:: Atomic\<T >](../standard-library/atomic.md) aus der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md).  
  
## <a name="end-of-iso-compliant"></a>Ende ISO-Kompatibilität  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Wenn die **angegebenem** -Compileroption verwendet wird – standardmäßig, wenn Architekturen als ARM adressiert werden, generiert der Compiler zusätzlichen Code, um die Reihenfolge der Verweise auf flüchtige Objekte zusätzlich zum Erhalt Reihenfolge für Verweise auf andere globale Objekte. Insbesondere:  
  
-   Das Schreiben in ein flüchtiges Objekt (auch als flüchtiger Schreibvorgang bezeichnet) weist Release-Semantik auf. Das heißt, dass ein Verweis auf ein globales oder statisches Objekt, das vor einem Schreibvorgang in ein flüchtiges Objekt in der Anweisungsabfolge auftritt, vor diesem flüchtigen Schreibvorgang in der kompilierten Binärdatei auftritt.  
  
-   Das Lesen eines flüchtigen Objekts (auch als flüchtiger Lesevorgang bezeichnet) weist Acquire-Semantik auf. Das heißt, dass ein Verweis auf ein globales oder statisches Objekt, das nach dem Lesevorgang eines flüchtigen Arbeitsspeichers in der Anweisungsabfolge auftritt, nach dem flüchtigen Lesevorgang in der kompilierten Binärdatei auftritt.  
  
 Dadurch können flüchtige Objekte für Arbeitsspeichersperren und -freigaben in Multithreadanwendungen verwendet werden.  
  
> [!NOTE]
>  Wenn das Prinzip basiert auf der erweiterten Garantie, die beim bereitgestellt hat die **angegebenem** -Compileroption verwendet wird, der Code ist nicht portabel.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const- und volatile-Zeiger](../cpp/const-and-volatile-pointers.md)