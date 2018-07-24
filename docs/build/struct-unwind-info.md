---
title: Struktur UNWIND_INFO | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: f0aee906-a1b9-44cc-a8ad-463637bd5411
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6046dffd74824b05c7b7b10be57bb0b2274ffdc
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2018
ms.locfileid: "39207571"
---
# <a name="struct-unwindinfo"></a>struct UNWIND_INFO
Die Entladung-Info-Datenstruktur wird verwendet, um die Auswirkungen zu erfassen, die eine Funktion verfügt, auf den Stack-Pointer und, in dem die nicht flüchtigen Register auf dem Stapel gespeichert werden:  
  
|||  
|-|-|  
|UBYTE: 3|Version|  
|UBYTE: 5|Flags|  
|UBYTE|Größe der prolog|  
|UBYTE|Anzahl von entladungscodes|  
|UBYTE: 4|Frame-Register|  
|UBYTE: 4|Frame-Register-Offset (skaliert)|  
|USHORT \* n|Entladen Sie Codes array|  
|Variable|Entweder kann der Form (1) oder (2) im folgenden werden|  
  
 (1) Ausnahmehandler  
  
|||  
|-|-|  
|ULONG|Adresse des ausnahmehandlers|  
|-Variable|Sprachspezifischer Handlerdaten (optional)|  
  
 (2) verkettet Entladeinformationen  
  
|||  
|-|-|  
|ULONG|Startadresse der Funktion|  
|ULONG|Funktion-Endadresse|  
|ULONG|Adresse der Entladeinformationen|  
  
 Die Struktur UNWIND_INFO muss DWORD im Arbeitsspeicher ausgerichtet sein. Die Bedeutung jedes Felds lautet wie folgt aus:  
  
 **Version**  
 Die Versionsnummer der Entladedaten, derzeit 1.  
  
 **Flags**  
 Aktuell sind drei Flags definiert:  
  
 UNW_FLAG_EHANDLER: die Funktion verfügt über einen Ausnahmehandler, der aufgerufen werden soll, beim Suchen nach Funktionen, die Ausnahmen zu analysieren.  
  
 UNW_FLAG_UHANDLER die Funktion verfügt über einen Beendigungshandler, der beim Entladen einer Ausnahme aufgerufen werden soll.  
  
 UNW_FLAG_CHAININFO diese Struktur ist nicht das primäre Replikat für die Prozedur Entladeinformationen. Stattdessen Entladeinformationen die verketteten, dass Eintrag auf den Inhalt eines vorherigen RUNTIME_FUNCTION Eintrags ist. Finden Sie unter den folgenden Text, eine Erläuterung der Verkettete Entladeinfostrukturen. Wenn dieses Flag festgelegt ist, müssen die UNW_FLAG_EHANDLER und UNW_FLAG_UHANDLER Flags deaktiviert werden. Darüber hinaus müssen die Frame-registrieren und -Stack Allocation-Felder die gleichen Werte wie in der primären Informationen zu entladen.  
  
 **Größe der prolog**  
 Die Länge des Funktionsprologs in Byte.  
  
 **Anzahl von entladungscodes**  
 Dies ist die Anzahl der Slots in das Array entladen. Beachten Sie, dass einige Codes (z. B. UWOP_SAVE_NONVOL) entladen erfordern mehr als einen Slot im Array.  
  
 **Frame-register**  
 Wert ungleich NULL ist, klicken Sie dann die Funktion Frame-Pointer verwendet, und dieses Feld gibt an, der nicht flüchtigen Register als der Frame-Pointer verwenden die gleiche Codierung für das Feld des Vorgangs Informationen Framezeiger verwendet.  
  
 **Frame erfassen Offset (skaliert)**  
 Wenn das Feld "Register" des Frame ungleich NULL ist, klicken Sie dann ist dies die skalierte Offset von RSP, die auf FP Reg angewendet wird, wenn es eingerichtet ist. Tatsächliche FP Reg nastaven NA hodnotu RSP + 16 \* diese Zahl, sodass die Offsets von 0 bis 240. Dies ermöglicht die FP Reg verweist, in die Mitte der lokalen stapelreservierung für dynamische Stapelrahmen, sodass eine höhere Dichte von Code mithilfe von kürzeren Anweisungen (Weitere Informationen können die signierten 8-Bit-Offset Formulars verwenden).  
  
 **Entladen Sie Codes array**  
 Dies ist ein Array von Elementen, die die Auswirkungen der Prolog auf die nicht flüchtigen Register und die RSP erläutert. Die Bedeutungen der einzelnen Elemente finden Sie im Abschnitt für UNWIND_CODE. Für die Ausrichtung weisen dieses Array immer eine gerade Anzahl von Einträgen, wobei der abschließende Eintrag möglicherweise nicht verwendet (in diesem Fall das Array eine länger als durch die Anzahl der Entladung Codes Feld gekennzeichnet werden).  
  
 **Adresse des ausnahmehandlers**  
 Dies ist ein Abbild relativ-Zeiger auf die Funktion sprachspezifische Ausnahme/Beendigungshandler (wenn Flag UNW_FLAG_CHAININFO nicht festgelegt, und eines der UNW_FLAG_EHANDLER oder UNW_FLAG_UHANDLER Flags festgelegt ist).  
  
 **Sprachspezifischer Handlerdaten**  
 Dies ist der Funktion sprachspezifischer Handler Ausnahmedaten. Das Format dieser Daten ist nicht angegeben und vollständig vom Handler für bestimmte Ausnahmen verwendet bestimmt.  
  
 **Verkettet Entladeinformationen**  
 Wenn das UNW_FLAG_CHAININFO-Flag festgelegt ist, und klicken Sie dann die UNWIND_INFO-Struktur mit drei UWORDs endet.  Diese UWORDs stellen die RUNTIME_FUNCTION Informationen für die Funktion die verketteten Entladung dar.  
  
## <a name="see-also"></a>Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)