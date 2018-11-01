---
title: Microsoft-Erweiterungen
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: d8104c2df2335e11dcb711108d566e0fdd069762
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50592204"
---
# <a name="microsoft-extensions"></a>Microsoft-Erweiterungen

*ASM-Anweisung*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm***Assemblyanweisung* **;** <sub>deaktivieren  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__asm {***Assembly-Anweisung-List***};** <sub>deaktivieren    </sub>

*Assembly-Anweisung-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Assembly-Anweisung* **;** <sub>deaktivieren</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Assembly-Anweisung* **;** *Assembly-Anweisung-List* **;** <sub>deaktivieren</sub>

*MS-Modifizierer-List*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*MS-Modifizierer* *ms-Modifizierer-List*<sub>deaktivieren</sub>

*MS-Modifizierer*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__syscall** (reserviert für zukünftige Implementierungen)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__oldcall** (reserviert für zukünftige Implementierungen)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__unaligned** (reserviert für zukünftige Implementierungen)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Basis-Modifizierer*

*Basis-Modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**__based (** *basierten Typ* **)**

*basierten Typ*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Name*