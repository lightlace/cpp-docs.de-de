---
title: Struktur RUNTIME_FUNCTION | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c2f28380d4a14cf7617653ede20468c45649a8b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="struct-runtimefunction"></a>struct RUNTIME_FUNCTION
Tabellenbasierte Ausnahmebehandlung erfordert einen Eintrag für alle Funktionen, die Stapelspeicher reservieren, oder rufen Sie eine andere Funktion (z. B. Nonleaf Funktionen). Funktionstabelleneinträge aufweisen Format:  
  
|||  
|-|-|  
|ULONG|Funktion-Startadresse|  
|ULONG|Funktion-Endadresse|  
|ULONG|Entladen Sie Info-Adresse|  
  
 Die RUNTIME_FUNCTION-Struktur muss DWORD im Arbeitsspeicher ausgerichtet sein. Alle Adressen sind relative Image, d. h. sie sind 32-Bit-Offsets von die Startadresse des Bilds, das den Funktionstabelleneintrag enthält. Diese Einträge sind sortiert, und fügen Sie in den .pdata-Abschnitt eines Bilds PE32 +. Für dynamisch generierte Funktionen [JIT-Compiler] muss die Laufzeit zur Unterstützung dieser Funktionen entweder RtlInstallFunctionTableCallback oder RtlAddFunctionTable verwenden diese Informationen für das Betriebssystem bereitstellen. Bei unterlassen, führt zu unzuverlässigen Behandlung von Ausnahmen und Debuggen von Prozessen.  
  
## <a name="see-also"></a>Siehe auch  
 [Entladedaten für die Ausnahmebehandlung, Debuggerunterstützung](../build/unwind-data-for-exception-handling-debugger-support.md)