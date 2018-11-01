---
title: 2.7.2.8 copyprivate
ms.date: 11/04/2016
ms.assetid: c382348c-c785-45b2-8ee6-a66b76b97f3e
ms.openlocfilehash: d4df1b4216014d3cd15be1480d2f83334fddb72d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622910"
---
# <a name="2728-copyprivate"></a>2.7.2.8 copyprivate

Die **Copyprivate** -Klausel bietet einen Mechanismus, um eine private Variable zu verwenden, um einen Wert von einem Mitglied eines Teams an den anderen Elementen zu übertragen. Es ist eine Alternative zur Verwendung von einer freigegebenen Variable für den Wert, wenn diese eine freigegebene Variable bereitstellen (z. B. in eine Rekursion, erfordern eine andere Variable auf jeder Ebene) schwierig wäre. Die **Copyprivate** Klausel kann nur verwendet werden, auf die **einzelne** Richtlinie.

Die Syntax der **Copyprivate** -Klausel ist wie folgt:

```

copyprivate(
variable-list
)

```

Die Auswirkungen der **Copyprivate** -Klausel für die Variablen in die Variablenliste tritt ein, nach der Ausführung von einem strukturierten Block zugeordnet der **einzelne** zu erstellen, und vor allen Threads in der Team die Grenze am Ende des Konstrukts verlassen haben. Klicken Sie auf alle anderen Threads im Team für jede Variable im der *Variablenliste*, diese Variable wird (wie durch Zuweisung) definiert, mit dem Wert der entsprechenden Variable in der der Thread, der das Konstrukt ausgeführt des strukturiert. Block.

Einschränkungen für die **Copyprivate** Klausel lauten wie folgt:

- Eine Variable, die im angegebenen die **Copyprivate** Klausel darf nicht erscheinen, eine **private** oder **Firstprivate** Klausel für den gleichen **einzelne**Richtlinie.

- Wenn eine **einzelne** -Direktive zusammen mit einer **Copyprivate** Klausel in der dynamischen Wertebereich eines parallelen Bereichs festgestellt wird, alle Variablen, die im angegebenen die **Copyprivate** -Klausel im umschließenden Kontext privat.

- Eine Variable, die im angegebenen die **Copyprivate** -Klausel muss ein zugänglich eindeutig Kopierzuweisungsoperator aufweisen.