---
title: C. 1-Notation | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a23b2631-8096-4bf3-ac23-ba4f4bd7a52a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d3ada700955c3acd2e96aa3e8a98c25c51393c1
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43766151"
---
# <a name="c1-notation"></a>C.1 Notation
Der Grammatikregeln für den bestehen aus des Namens für eine nicht-Terminal, gefolgt von einem Doppelpunkt, gefolgt von Ersatz alternativen in separaten Zeilen.

Die syntaktische Ausdruck<sub>opt</sub> gibt an, dass der Begriff innerhalb die Ersetzung optional ist.

Der syntaktischen Ausdruck *Begriff*<sub>Optseq</sub> entspricht *Begriff-Seq*<sub>opt</sub> mit den folgenden zusätzlichen Regeln:

*Laufzeit-Seq* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Begriff*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Laufzeit-Seq* *Begriff*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Laufzeit-Seq* **,** *Begriff*