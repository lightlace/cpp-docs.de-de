---
title: Volatile (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 43
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 02560da98c583281cc05921f2e924a12f41688c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="volatile-c"></a>volatile (C++)
Ein Typqualifizierer, den Sie verwenden können, um zu deklarieren, dass ein Objekt im Programm von der Hardware geändert werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
volatile declarator ;  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können die [/volatile](../build/reference/volatile-volatile-keyword-interpretation.md) Compilerschalter ändern, wie der Compiler dieses Schlüsselwort interpretiert.  
  
 Visual Studio interpretiert das `volatile`-Schlüsselwort je nach Zielarchitektur unterschiedlich. Für ARM, wenn keine **/volatile** -Compileroption angegeben ist, führt der Compiler als **/volatile:iso** angegeben wurden. Für andere Architekturen als ARM, wenn keine **/volatile** -Compileroption angegeben ist, führt der Compiler als **/volatile:ms** angegeben wurden; daher für Architekturen als ARM dringend Es wird empfohlen, die Sie angeben, **/volatile:iso**, und explizite Synchronisierungsprimitiven und systeminterne Compilerfunktionen zu verwenden, wenn Sie mit Arbeitsspeicher arbeiten, der über Threads freigegeben wird.  
  
 Sie können den `volatile`-Qualifizierer verwenden, um den Zugriff auf die Speicherbereiche zu ermöglichen, die von asynchronen Prozessen wie Interrupthandlern verwendet werden.  
  
 Wenn `volatile` wird verwendet, auf eine Variable, die verfügt auch über die [__restrict](../cpp/extension-restrict.md) -Schlüsselwort, `volatile` hat Vorrang vor.  
  
 Wenn ein `struct`-Member als `volatile` gekennzeichnet ist, dann wird `volatile` an die gesamte Struktur weitergegeben. Wenn eine Struktur nicht über eine Länge verfügt, die mithilfe einer Anweisung in der aktuellen Architektur kopiert werden kann, geht `volatile` in dieser Struktur möglicherweise vollständig verloren.  
  
 Das `volatile`-Schlüsselwort hat möglicherweise keine Auswirkungen auf ein Feld, wenn eine der folgenden Bedingungen zutrifft:  
  
-   Die Länge des flüchtigen Felds überschreitet die maximale Größe, die in der aktuellen Architektur mithilfe einer Anweisung kopiert werden kann.  
  
-   Die Länge der äußersten enthaltenen `struct` – oder wenn es sich um einen Member einer möglicherweise geschachtelten `struct` handelt – überschreitet die maximale Größe, die in der aktuellen Architektur mithilfe einer Anwendung kopiert werden kann.  
  
 Obwohl der Prozessor Speicherzugriffe, die nicht zwischengespeichert werden können, nicht neu anordnet, müssen Variablen, die nicht zwischengespeichert werden können, als `volatile` gekennzeichnet werden, um sicherzustellen, dass der Compiler die Speicherzugriffe nicht neu anordnet.  
  
 Objekte, die als `volatile` deklariert werden, werden in bestimmten Optimierungen nicht verwendet, da sich ihre Werte jederzeit ändern können.  Das System liest bei jeder Anforderung den aktuellen Wert eines flüchtigen Objekts, selbst wenn eine vorherige Anweisung bereits den Wert des gleichen Objekts abgefragt hatte.  Außerdem wird der Wert des Objekts sofort durch Zuweisung geschrieben.  
  
## <a name="iso-compliant"></a>ISO-Kompatibilität  
 Wenn Sie vertraut sind, mit der C#-volatile-Schlüsselwort oder mit dem Verhalten von vertraut sind `volatile` in früheren Versionen von Visual C++, Bedenken Sie, dem C ++ 11 ISO-Standard `volatile` Schlüsselwort unterscheidet sich und wird in Visual Studio unterstützt beim der [/ Volatile: Iso](../build/reference/volatile-volatile-keyword-interpretation.md) -Compileroption angegeben ist. (In ARM ist es standardmäßig festgelegt). Das `volatile`-Schlüsselwort im ISO-Standardcode C++11 wird nur für Hardwarezugriffe verwendet. Verwenden Sie es nicht für die Kommunikation zwischen Threads. Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [Std:: Atomic\<T >](../standard-library/atomic.md) aus der [C++-Standardbibliothek](../standard-library/cpp-standard-library-reference.md).  
  
## <a name="end-of-iso-compliant"></a>Ende ISO-Kompatibilität  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Wenn die **/volatile:ms** -Compileroption verwendet wird – Standard, wenn andere Architekturen als ARM adressiert werden, generiert der Compiler zusätzlichen Code, um die Reihenfolge der Verweise auf flüchtige Objekte zusätzlich zum Erhalt zu verwalten Reihenfolge von Verweisen auf andere globale Objekte. Insbesondere:  
  
-   Das Schreiben in ein flüchtiges Objekt (auch als flüchtiger Schreibvorgang bezeichnet) weist Release-Semantik auf. Das heißt, dass ein Verweis auf ein globales oder statisches Objekt, das vor einem Schreibvorgang in ein flüchtiges Objekt in der Anweisungsabfolge auftritt, vor diesem flüchtigen Schreibvorgang in der kompilierten Binärdatei auftritt.  
  
-   Das Lesen eines flüchtigen Objekts (auch als flüchtiger Lesevorgang bezeichnet) weist Acquire-Semantik auf. Das heißt, dass ein Verweis auf ein globales oder statisches Objekt, das nach dem Lesevorgang eines flüchtigen Arbeitsspeichers in der Anweisungsabfolge auftritt, nach dem flüchtigen Lesevorgang in der kompilierten Binärdatei auftritt.  
  
 Dadurch können flüchtige Objekte für Arbeitsspeichersperren und -freigaben in Multithreadanwendungen verwendet werden.  
  
> [!NOTE]
>  Wenn sie abhängig von der erweiterten Garantie, die beim bereitgestellt hat die **/volatile:ms** -Compileroption verwendet wird, der Code ist nicht portabel.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const- und volatile-Zeiger](../cpp/const-and-volatile-pointers.md)