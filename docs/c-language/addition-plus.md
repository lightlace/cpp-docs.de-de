---
title: Addition (+) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pointers, adding integers
ms.assetid: b9014fee-825d-46ef-91db-5d46807081fc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 62ed952113f3d8b3db46ac735ade4d2e9850dc97
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090853"
---
# <a name="addition-"></a>Addition (+)

Der Additionsoperator (**+**) sorgt dafür, dass seine beiden Operanden hinzugefügt werden. Beide Operanden können entweder vom Typ „Ganze Zahl“ oder „Gleitkommazahl“ sein, oder ein Operand kann ein Zeiger und der andere eine ganze Zahl sein.

Wenn eine ganze Zahl zu einem Zeiger addiert wird, wird der Ganzzahlwert (*i*) konvertiert, indem er mit der Größe des Werts multipliziert wird, auf den der Zeiger zeigt. Nach der Konvertierung stellt der ganzzahlige Wert *i* Arbeitsspeicherpositionen dar, wobei jede Position über die Länge verfügt, die vom Zeigertyp angegeben wird. Wenn der konvertierte Ganzzahlwert zum Zeigerwert addiert wird, ist das Ergebnis ein neuer Zeigerwert, der die Adresse in der Entfernung von *i* Positionen von der ursprünglichen Adresse darstellt. Der neue Zeigerwert gibt den Wert desselben Typs an, der vom ursprüngliche Zeigerwert adressiert wurde. Dieser Wert gleicht der Arrayindizierung (siehe [Eindimensionale Arrays](../c-language/one-dimensional-arrays.md) und [Mehrdimensionale Arrays](../c-language/multidimensional-arrays-c.md)). Wenn der Summenzeiger über das Array hinaus zeigt (außer auf die erste Position oberhalb des oberen Grenzwerts), ist das Ergebnis nicht definiert. Weitere Informationen finden Sie unter [Zeigerarithmetik](../c-language/pointer-arithmetic.md).

## <a name="see-also"></a>Siehe auch

[C-Operatoren (additiv)](../c-language/c-additive-operators.md)