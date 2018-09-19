---
title: Microsoft-Erweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- Microsoft extensions to C/C++
ms.assetid: 68654516-24ef-4f33-aae2-175f86cc1979
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5699ce82a6e8537f12da50fdcb8288da167ecca3
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43752238"
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