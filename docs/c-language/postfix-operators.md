---
title: Postfix-Operatoren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C], postfix
- postfix operators
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 338e518d1939cb6ea32aaf200c54b6c352287561
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43760262"
---
# <a name="postfix-operators"></a>Postfix-Operatoren
Die Postfix-Operatoren weisen den höchsten Rang (die festeste Bindung) in der Ausdrucksauswertung auf.  

## <a name="syntax"></a>Syntax

*postfix-expression*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*primary-expression*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **[**  *expression*  **]**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **(**  *argument-expression-list*<sub>opt</sub> **)**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **.**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **->**  *identifier*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **++**<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*postfix-expression*  **--**

Operatoren in dieser Rangfolgenebene sind die Arrayfeldindizes, Funktionsaufrufe, die Struktur- und Union-Member sowie Postfix-Operatoren für Inkrement und Dekrement.

## <a name="see-also"></a>Siehe auch

[C-Operatoren](../c-language/c-operators.md)