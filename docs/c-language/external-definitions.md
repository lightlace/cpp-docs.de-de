---
title: Externe Definitionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- external definitions
- external linkage, variable declarations
ms.assetid: 41e37bfc-b360-43b1-9972-28af2d365b20
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 193ba8b853fbdbe16f906e1cdf82dd22a40f36bb
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43759495"
---
# <a name="external-definitions"></a>Externe Definitionen

*translation-unit*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*external-declaration* <br/>
&nbsp;&nbsp;&nbsp;&nbsp;*translation-unit* *external-declaration*  
  
*external-declaration*: /\* Nur für externen (Datei-) Bereich zulässig \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*function-definition*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration*

*function-definition*: /\* Der Deklarator hier ist der Funktionsdeklarator \*/<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*declaration-specifiers*<sub>opt</sub> *declarator* *declaration-list*<sub>opt</sub> *compound-statement*

## <a name="see-also"></a>Siehe auch

[Phrasenstrukturgrammatik](../c-language/phrase-structure-grammar.md)