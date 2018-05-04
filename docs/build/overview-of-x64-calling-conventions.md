---
title: Übersicht über die X64 Aufrufkonventionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a05db5eb-0844-4d9d-8b92-b1b2434be0ea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb4071cd3223ad2ab073f84418e641b515c05112
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="overview-of-x64-calling-conventions"></a>Übersicht über x64-Aufrufkonventionen
Zwei wichtige Unterschiede zwischen X86 und [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] werden die 64-Bit-Adressierung-Funktion und eine flache Reihe von 16 64-Bit-registriert wird, zur allgemeinen Verwendung. Registrieren Sie aufgrund des erweiterten Menge [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] verwendet die [__fastcall](../cpp/fastcall.md) Aufrufkonvention und ein Ausnahmebehandlungsmodell RISC-basierten. Die `__fastcall` Konvention verwendet Register für die ersten vier Argumente und den Stapelrahmen, um zusätzliche Argumente zu übergeben.  
  
 Die folgende Compileroption können Sie die Optimierung der Anwendung für [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]:  
  
-   [/favor (Für Architektureigenschaften optimieren)](../build/reference/favor-optimize-for-architecture-specifics.md)  
  
## <a name="calling-convention"></a>Aufrufkonvention  
 Die [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] Anwendung binären Schnittstelle (ABI) eine Aufrufkonvention für die vier Register Fast-Aufruf wird standardmäßig verwendet. Speicherplatz wird in der Aufrufliste als Schatten Speicher für den aufgerufenen diese Register speichern zugeordnet. Es ist eine strenge 1: 1-Entsprechung zwischen den Argumenten zu einem Funktionsaufruf und die für diese Argumente zu verwendenden Register. Ein der Argumente, das 8 Bytes passt nicht oder ist nicht 1, 2, 4 oder 8 Bytes festgelegt, muss als Verweis übergeben werden. Es gibt keinen Versuch, ein einzelnes Argument auf mehrere Register zu verteilen. Die X87 Registerstapel wird nicht verwendet. Von der aufgerufenen Instanz verwendet werden kann, aber muss bei Funktionsaufrufen volatile berücksichtigt werden. Alle Gleitkommazahlen Vorgänge erfolgen mithilfe der 16 XMM-Register. Ganzzahlige Argumente werden in Registern RCX, RDX, R8 oder R9 übergeben. Gleitkommaoptionen XMM0L, XMM1L XMM2L und XMM3L Argumente übergeben werden. 16-Byte-Argumente werden als Verweis übergeben. Übergeben von Parametern wird ausführlich beschrieben unter [Parameterübergabe](../build/parameter-passing.md). Zusätzlich zu diesen Registern RAX, R10, R11, XMM4 und XMM5 flüchtig gelten. Alle anderen Register sind, nicht flüchtigem. Registernutzung wird ausführlich dokumentiert [registrieren Sie Verbrauch](../build/register-usage.md) und [Aufrufer-/Aufgerufener gespeichert registriert](../build/caller-callee-saved-registers.md).  
  
 Der Aufrufer ist verantwortlich für das Zuweisen von Speicherplatz für Parameter an die aufgerufenen und muss immer ausreichend Speicherplatz zum Speichern von vier Registerparameter zuordnen, auch wenn der aufgerufene viele Parameter akzeptiert. Dies vereinfacht die Unterstützung für die Programmiersprache C Funktionen ohne Prototyp und Vararg-C/C++-Funktionen. Vararg oder ohne Prototyp-Funktionen, alle Gleitkommazahlen Werte müssen im entsprechenden Allzweckregister dupliziert werden. Alle Parameter über die ersten vier müssen auf dem Stapel, über den Volumeschattenkopie-Speicher für die ersten vier, vor dem Aufruf gespeichert werden. Vararg-Funktionsdetails finden Sie [Varargs](../build/varargs.md). Ohne Prototyp Funktionsinformationen finden Sie unter [Funktionen ohne Prototyp](../build/unprototyped-functions.md).  
  
## <a name="alignment"></a>Ausrichtung  
 Die meisten Strukturen werden gemäß ihrer natürlichen Ausrichtung ausgerichtet. Die wichtigsten Ausnahmen sind der Stapelzeiger und `malloc` oder `alloca` Arbeitsspeicher, die auf 16 Bytes ausgerichtet werden, um die Leistung zu unterstützen. Ausrichtung auf mehr als 16 Bytes muss manuell erfolgen, aber da 16 Bytes ist eine allgemeine Ausrichtungsgröße für XMM-Vorgänge, sollte dies für die meisten Code funktioniert. Weitere Informationen zu Struktur Layout- und ausrichtungsverwaltung finden Sie unter [Typen und Speicher](../build/types-and-storage.md). Informationen über das Stapellayout finden Sie unter [Stapelverwendung](../build/stack-usage.md).  
  
## <a name="unwindability"></a>Unwindability  
 Funktionen sind Funktionen, die alle nicht flüchtigen Register nicht ändern. Eine innerer-Funktion kann nicht flüchtigen RSP, z. B. ändern, indem eine Funktion aufrufen, oder weisen Sie zusätzlichen Stapelspeicher für lokale Variablen. Um nicht flüchtigen Register wiederherstellen, wenn eine Ausnahme behandelt wird, müssen nichtblatt-Funktionen mit statischen Daten kommentiert werden, die beschreibt, wie ordnungsgemäß Entladung der Funktion an eine beliebige Anweisung. Diese Daten werden als gespeichert *Pdata*, oder Prozedur Daten bezieht sich wiederum auf *Xdata*, die Daten für die Ausnahmebehandlung. Die Xdata enthält die entladen und auf zusätzliche Pdata bzw. eine Ausnahme Handlerfunktion verweisen. Prologe und Epiloge sind stark eingeschränkte, damit sie ordnungsgemäß in Xdata beschrieben werden können. Der Stapelzeiger muss auf 16 Bytes in einer beliebigen Region Code ausgerichtet werden, die nicht Teil eines Epilogs oder Prolog, außer in Funktionen. Funktionen können entladen werden, indem Sie einfach eine Rückgabe simulieren, sodass Pdata und Xdata nicht erforderlich sind. Ausführliche Informationen über die richtige Struktur der Funktion Prologe und Epiloge finden Sie unter [Prolog und Epilog](../build/prolog-and-epilog.md). Weitere Informationen zur Behandlung von Ausnahmen und die Ausnahme behandeln und Entladen von Pdata und Xdata finden Sie unter [Exception Handling (x64)](../build/exception-handling-x64.md).  
  
## <a name="see-also"></a>Siehe auch  
 [x64-Softwarekonventionen](../build/x64-software-conventions.md)