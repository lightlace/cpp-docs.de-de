---
title: Microsoft-Erweiterungen
ms.date: 11/04/2016
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
ms.openlocfilehash: d8104c2df2335e11dcb711108d566e0fdd069762
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301772"
---
# <a name="microsoft-extensions"></a>Microsoft-Erweiterungen

*asm-statement*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm** *Assemblyanweisung* **;** <sub>deaktivieren  </sub><br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__asm {** *Assembly-Anweisung-List* **};** <sub>deaktivieren    </sub>

*assembly-instruction-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assembly-instruction* **;** <sub>opt</sub> <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*assembly-instruction* **;** *assembly-instruction-list* **;** <sub>opt</sub>

*ms-modifier-list*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*ms-modifier* *ms-modifier-list*<sub>opt</sub>

*ms-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__cdecl**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__fastcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__stdcall**<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__syscall** (reserviert für zukünftige Implementierungen)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__oldcall** (reserviert für zukünftige Implementierungen)<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__unaligned** (reserviert für zukünftige Implementierungen)<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*based-modifier*

*based-modifier*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp; **__based (** *based-type* **)**

*based-type*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Name*