---
title: Übersicht über die X64 Aufrufkonventionen | Microsoft-Dokumentation
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
ms.openlocfilehash: e70f4017cb31fcc76b1cf3ef2a77d3a28e31bd28
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707992"
---
# <a name="overview-of-x64-calling-conventions"></a>Übersicht über x64-Aufrufkonventionen

Zwei wichtige Unterschiede zwischen X86- und X64 werden die 64-Bit-Adressierung-Funktion und ein Satz von 16 64-Bit-Flatfile zur allgemeinen Verwendung registriert. Bei Verwendung der erweiterten Register-Gruppe, X64 verwendet werden. die [__fastcall](../cpp/fastcall.md) Aufrufkonvention und ein Ausnahmebehandlungsmodell RISC-basierten. Die `__fastcall` Konvention verwendet führt die Registrierung für die ersten vier Argumente und den Stapelrahmen, um zusätzliche Argumente übergeben.

Die folgende Compileroption können Sie Ihre Anwendung für X64 zu optimieren:

- [/favor (Für Architektureigenschaften optimieren)](../build/reference/favor-optimize-for-architecture-specifics.md)

## <a name="calling-convention"></a>Aufrufkonvention

Standardmäßig verwendet die X64 verwendeten Application Binary Interface (ABI) eine vier-Register Aufrufkonvention Fast-Aufruf durch. Speicherplatz wird in der Aufrufliste als Schattenkopien Speicher für den aufgerufenen zum Speichern dieser Register zugeordnet. Es gibt strict eins zu eins entsprechen zwischen den Argumenten auf ein Funktionsaufruf und die für diese Argumente zu verwendenden Register ein. Ein der Argumente, das 8 Bytes passt nicht oder ist nicht 1, 2, 4 oder 8 Bytes, die muss als Verweis übergeben werden. Es gibt keinen Versuch, ein einzelnes Argument auf mehrere Registrierungen zu verteilen. Die X87 Registerstapel wird nicht verwendet. Es kann von der aufgerufenen Instanz verwendet werden, aber Sie müssen bei Funktionsaufrufen flüchtige berücksichtigt werden. Alle Gleitkommawerte Vorgänge erfolgen mithilfe der 16 XMM-Register. Es werden ganzzahlige Argumente in Registern RCX, RDX, R8 und R9 übergeben. Gleitkommaoptionen XMM0L, XMM1L, XMM2L und XMM3L Argumente übergeben werden. 16-Byte-Argumente werden als Verweis übergeben. Übergeben von Parametern ist ausführlich im [Parameterübergabe](../build/parameter-passing.md). Zusätzlich zu diesen Registerkarten RAX, R10, R11, XMM4 und XMM5 flüchtige gelten. Alle anderen Register sind nicht flüchtig. Registernutzung wird ausführlich dokumentiert [Verwendung registrieren](../build/register-usage.md) und [Aufrufer-/Aufgerufener gespeichert registriert](../build/caller-callee-saved-registers.md).

Der Aufrufer ist für die datenträgerzuweisung für Parameter an den aufgerufenen verantwortlich und muss immer ausreichend Speicherplatz zum Speichern von vier Registerparameter zuordnen, auch wenn der aufgerufene viele Parameter verwendet werden. Dies vereinfacht die Unterstützung für die Programmiersprache C Funktionen ohne Prototyp und Vararg-C/C++-Funktionen. Für Vararg-ohne Prototyp-Funktionen Gleitkommawerte müssen Werte, die in der entsprechenden Allzweckregister dupliziert werden. Alle Parameter über die ersten vier müssen auf dem Stapel, über den Volumeschattenkopie-Speicher für die ersten vier, vor dem Aufruf gespeichert werden. Vararg-Funktion Informationen finden Sie [Varargs](../build/varargs.md). Ohne Prototyp-Funktionsinformationen finden Sie im [Funktionen ohne Prototyp](../build/unprototyped-functions.md).

## <a name="alignment"></a>Ausrichtung

Die meisten Strukturen werden gemäß ihrer natürlichen Ausrichtung ausgerichtet. Die wichtigsten Ausnahmen sind der Stapelzeiger und `malloc` oder `alloca` Arbeitsspeicher, die auf 16-Byte-ausgerichtet werden, um Leistung zu unterstützen. Ausrichtung auf mehr als 16 Bytes muss manuell durchgeführt werden, aber da es 16 Bytes handelt es sich um eine Ausrichtung-Standardgröße für XMM-Vorgänge, sollte dies für die meisten Code funktionieren. Weitere Informationen zu Struktur Layout- und ausrichtungsverwaltung finden Sie unter [Typen und Speicher](../build/types-and-storage.md). Weitere Informationen über das Layout der Stack finden Sie unter [Stapelverwendung](../build/stack-usage.md).

## <a name="unwindability"></a>Unwindability

Funktionen sind Funktionen, die alle nicht flüchtigen Register nicht ändern. Eine innerer-Funktion kann nicht flüchtigen RSP, z. B. ändern, durch Aufrufen einer Funktion oder das Zuordnen von zusätzlichen Stapelspeicher für lokale Variablen. Um nicht flüchtigen Register wiederherzustellen, wenn eine Ausnahme behandelt wird, müssen der nichtblatt-Funktionen mit statischen Daten kommentiert werden, die beschreibt, wie Sie zu die Funktion an eine beliebige Anweisung ordnungsgemäß zu entladen. Diese Daten werden gespeichert, als *Pdata*, oder Prozedur Daten bezieht sich wiederum auf *Xdata*, die Daten für die Ausnahmebehandlung. Die Xdata enthält Informationen, die entladen und auf zusätzliche Pdata bzw. eine ausnahmehandlerfunktion verweisen. Prologe und Epiloge sind sehr eingeschränkten, damit sie ordnungsgemäß in Xdata beschrieben werden können. Der Stapelzeiger muss auf 16 Bytes in einer beliebigen Region Code ausgerichtet werden, die nicht im Rahmen eines Prolog oder Epilog mit Ausnahme von Funktionen. Funktionen können entladen werden, indem Sie einfach eine Rückgabe simuliert, sodass Pdata und Xdata nicht erforderlich sind. Weitere Informationen über die richtige Struktur von Funktion prologen und epilogen, finden Sie unter [Prolog und Epilog](../build/prolog-and-epilog.md). Weitere Informationen zur Behandlung von Ausnahmen und die Behandlung von Ausnahmen und stapelentladung Pdata und Xdata finden Sie unter [Exception Handling (x64)](../build/exception-handling-x64.md).

## <a name="see-also"></a>Siehe auch

[x64-Softwarekonventionen](../build/x64-software-conventions.md)