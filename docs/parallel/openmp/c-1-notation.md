---
title: C.1 Notation
ms.date: 11/04/2016
ms.assetid: a23b2631-8096-4bf3-ac23-ba4f4bd7a52a
ms.openlocfilehash: 593450b6dd7dcb30adbf8546ad96ff716c6fbc1c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473982"
---
# <a name="c1-notation"></a>C.1 Notation

Der Grammatikregeln für den bestehen aus des Namens für eine nicht-Terminal, gefolgt von einem Doppelpunkt, gefolgt von Ersatz alternativen in separaten Zeilen.

Die syntaktische Ausdruck<sub>opt</sub> gibt an, dass der Begriff innerhalb die Ersetzung optional ist.

Der syntaktischen Ausdruck *Begriff*<sub>Optseq</sub> entspricht *Begriff-Seq*<sub>opt</sub> mit den folgenden zusätzlichen Regeln:

*Laufzeit-Seq* :<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Begriff*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Laufzeit-Seq* *Begriff*<br/>
&nbsp;&nbsp;&nbsp;&nbsp;*Laufzeit-Seq* **,** *Begriff*