---
title: Struktur RUNTIME_FUNCTION | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 476ce4ad532f1e02b8863e2276fe0300c5895270
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
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