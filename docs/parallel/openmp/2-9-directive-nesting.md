---
title: 2.9 Schachtelung von Anweisungen
ms.date: 11/04/2016
ms.assetid: 6565a43c-fd2d-4366-8322-8d75e1b06600
ms.openlocfilehash: 804cafd65fde19e501b89c47925f471143d74938
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438726"
---
# <a name="29-directive-nesting"></a>2.9 Schachtelung von Anweisungen

Dynamische Schachtelung von Anweisungen muss die folgenden Regeln beachtet werden:

- Ein **parallele** dynamisch in einer anderen Richtlinie **parallele** logisch richtet ein neues Team, das nur den aktuellen Thread besteht, es sei denn, die Parallelität geschachtelt ist aktiviert.

- **für**, **Abschnitte**, und **einzelne** Direktiven, die auf die gleiche Bindung **parallele** dürfen nicht ineinander geschachtelt werden.

- **kritische** Anweisungen mit dem gleichen Namen dürfen nicht ineinander geschachtelt werden. Beachten Sie, dass diese Einschränkung ist nicht ausreichend, Deadlocks zu vermeiden.

- **für**, **Abschnitte**, und **einzelne** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **kritische**, **sortiert**, und **master** Regionen aus, wenn die Anweisungen auf die gleiche Bindung **parallele** als Regionen.

- **Barriere** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **für**, **sortiert**, **Abschnitte**, **einzelne**, **master**, und **kritische** Regionen aus, wenn die Anweisungen auf die gleiche Bindung **parallele** als Regionen.

- **Master** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **für**, **Abschnitte**, und **einzelne** Direktiven Wenn die **Master** Anweisungen zu binden, auf die gleiche **parallele** als die gemeinsame Verwendung von Work-Anweisungen.

- **sortiert** Anweisungen sind nicht zulässig, in der dynamischen Wertebereich **kritische** Regionen aus, wenn die Anweisungen auf die gleiche Bindung **parallele** als Regionen.

- Jede Richtlinie, die zulässig ist, wenn dynamisch innerhalb eines parallelen Bereichs ausgeführt ist auch zulässig, wenn außerhalb eines parallelen Bereichs ausgeführt. Wenn außerhalb eines parallelen Bereichs von benutzerdefinierten dynamisch ausgeführt wird, wird die Richtlinie von einem Team besteht aus nur die master-Thread ausgeführt.