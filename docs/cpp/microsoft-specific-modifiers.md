---
title: Microsoft-spezifische Modifizierer | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 22c7178c-f854-47fa-9de6-07d23fda58e1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8490a50f30d366a53a9e3288417a8d83032c556d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="microsoft-specific-modifiers"></a>Microsoft-spezifische Modifizierer
Dieser Abschnitt beschreibt Microsoft-spezifische Erweiterungen von C++ in den folgenden Bereichen:  
  
-   [Basierende Adressierung](../cpp/based-addressing.md), das Geübte mithilfe eines Zeigers als Basis von der andere Zeiger versetzt werden können  
  
-   [Funktion-Aufrufkonventionen](../cpp/calling-conventions.md)  
  
-   Erweiterte speicherklassenattribute deklariert, mit der [__declspec](../cpp/declspec.md) Schlüsselwort  
  
-   Die [__w64](../cpp/w64.md) Schlüsselwort  
  
 Viele der Microsoft-spezifischen Schlüsselwörter können verwendet werden, um Deklaratoren zum Bilden abgeleiteter Typen zu ändern. Weitere Informationen über Deklaratoren finden Sie unter [Deklaratoren](http://msdn.microsoft.com/en-us/8a7b9b51-92bd-4ac0-b3fe-0c4abe771838).  
  
### <a name="microsoft-specific-keywords"></a>Microsoft-spezifische Schlüsselwörter  
  
|Stichwort|Bedeutung|Wird verwendet, um abgeleitete Typen zu bilden?|  
|-------------|-------------|---------------------------------|  
|[__based](../cpp/based-grammar.md)|Der folgende Name deklariert ein 32-Bit-Offset zur 32-Bit-Basis in der Deklaration.|Ja|  
|[__cdecl](../cpp/cdecl.md)|Der folgende Name verwendet C-Benennungs- und C-Aufrufkonventionen.|Ja|  
|[__declspec](../cpp/declspec.md)|Der folgende Name gibt ein Microsoft-spezifisches Speicherklassenattribut an.|Nein|  
|[__fastcall](../cpp/fastcall.md)|Der folgende Name deklariert eine Funktion, die Register verwendet, sofern verfügbar, anstatt des Stapels für die Argumentübergabe.|Ja|  
|[__restrict](../cpp/extension-restrict.md)|Ähnlich wie __declspec ([beschränken](../cpp/restrict.md)), aber für die Verwendung von Variablen.|Nein|  
|[__stdcall](../cpp/stdcall.md)|Der folgende Name gibt eine Funktion an, die herkömmliche Aufrufkonventionen berücksichtigt.|Ja|  
|[__w64](../cpp/w64.md)|Markiert einen Datentyp als größer bei einem 64-Bit-Compiler.|Nein|  
|[__unaligned](../cpp/unaligned.md)|Gibt an, dass ein Zeiger auf einen Typ oder andere Daten nicht ausgerichtet ist.|Nein|  
|[__vectorcall](../cpp/vectorcall.md)|Der folgende Name deklariert eine Funktion, die Register, einschließlich SSE-Register, verwendet, sofern diese verfügbar sind, anstatt des Stapels für die Argumentübergabe.|Ja|  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)